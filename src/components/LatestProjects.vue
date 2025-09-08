<script setup lang="ts">
import { ref, onMounted } from 'vue';
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { ZoomInIcon } from 'lucide-vue-next';
import TitleSection from '@/components/TitleSection.vue';
import VueEasyLightbox from 'vue-easy-lightbox';


interface ProjectItem {
  title: string;
  description: string;
  image: string;
}

const items = ref<ProjectItem[]>([]);

const parseXml = (xmlString: string): ProjectItem[] => {
  const parser = new DOMParser()
  const xmlDoc = parser.parseFromString(xmlString, 'text/xml')
  const itemsArray: ProjectItem[] = []

  // Adjust the selector based on your XML structure
  const itemNodes = xmlDoc.getElementsByTagName('item')
  
  Array.from(itemNodes).forEach(node => {
    itemsArray.push({
      title: node.getElementsByTagName('title')[0]?.textContent || '',
      description: node.getElementsByTagName('description')[0]?.textContent || '',
      image: node.getElementsByTagName('image')[0]?.textContent || ''
    })
  })
  
  return itemsArray
}

onMounted(async () => {
  try {
    const response = await fetch('/latest-projects-data.xml')
    const xmlString = await response.text()
    items.value = parseXml(xmlString)
  } catch (error) {
    console.error('Error loading XML:', error)
  }
})

// Project images (can be in /src/assets or /public/images)

const visible = ref(false)
const index = ref(0)

const open = (i: number) => {
  index.value = i
  visible.value = true
}
</script>

<template>
    <TitleSection title="Latest Projects" subtitle="Check out our latest projects"/>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <Card v-for="(item, index) in items" :key="index" class="gap-0">
            <CardHeader>
                <CardTitle class="text-lg">{{ item.title }}</CardTitle>
            </CardHeader>
            <CardContent class="px-0">
                <CardDescription>{{ item.description }}</CardDescription>
                <img :src="item.image" :alt="item.title"
                    class="mt-4 rounded w-full aspect-video object-cover object-top" />
            </CardContent>
            <CardFooter class="pt-4">
                <Button type="button" variant="default" @click="open(index)">View Project
                    <ZoomInIcon />
                </Button>
            </CardFooter>
        </Card>
    </div>
    <!-- Lightbox Component -->
    <VueEasyLightbox
      :visible="visible"
      :imgs="items.map(item => item.image)"
      :index="index"
      @hide="visible = false"
    />
</template>