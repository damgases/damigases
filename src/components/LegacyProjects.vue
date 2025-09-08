<script setup lang="ts">
import { ref, onMounted } from 'vue';
import {  Card,  CardContent } from "@/components/ui/card";
import TitleSection from '@/components/TitleSection.vue';


interface ProjectItem {
  title: string;
  description: string;
  image: string;
}

const items = ref<ProjectItem[]>([]);
const itemsCount = ref<number>(21);

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
</script>

<template>
    <TitleSection title="Legacy Projects" subtitle="Check out our latest projects"/>
    <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-4">
        <Card class="gap-0" v-for="i in itemsCount" :key="i" :class="'p-0 overflow-hidden'">
            <!-- <CardHeader>
                <CardTitle class="text-lg">{{ item.title }}</CardTitle>
            </CardHeader> -->
            <CardContent class="px-0">
                <!-- <CardDescription>{{ item.description }}</CardDescription> -->
                <img :src="'images/port_' + i + '.jpg'" :alt="'Project ' + i"
                    class="rounded w-full aspect-video object-cover object-top" />
            </CardContent>
            <!-- <CardFooter class="pt-4">
                <Button type="button" variant="default">View Project
                    <ZoomInIcon />
                </Button>
            </CardFooter> -->
        </Card>
    </div>
</template>