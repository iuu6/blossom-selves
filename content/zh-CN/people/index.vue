<template>
  <main class="xl:max-w-[980px] max-w-7/8 mx-auto">
    <section v-for="[title, work] in Object.entries(people)" :key="title">
      <h1 class="text-[1.2rem] text-gray-500 mt-10">
        {{ title }}
      </h1>
      <VPFeatures :features="work" class="my-6 px-0!" />
    </section>
  </main>
</template>
<script setup lang="ts">
import type { Feature } from 'vitepress/dist/client/theme-default/components/VPFeatures.vue';
import VPFeatures from 'vitepress/dist/client/theme-default/components/VPFeatures.vue';

interface People {
  // index string , value Feature
  [index: string]: Feature[];
}

const people: People = {
  'Meet the Team!': [
    {
      title: '小魔 (She/Her)',
      details:
        '「万物许可，顺随，完美。」Blossom Selves组织者',
      link: 'https://cdn5.telesco.pe/file/JByt0C76yv8Y5j2CoJKhnGfhHzAunNJjjptxnKwpMZG5hDAG4LhrOki-KVe19zShiABm-n2AreKje38U0766QLPnNa2Mw-KRWtXuGwRqY7X3ttXCAHOA1BPEz8dXkFte7AiCc8QAhEqLP7RXqXfoRm5Sb9KpdZ4rI9t0CVSRd8OFnxQeIkoLCScwko4gTxqFu3FXL_ke2QAZdLRCDqjfDDxuTjHFM3DwMQRn778T11bX6FhisPVjmXtnxQJR9LTBDph1tgKVUP1y7fsXV50YBHOix6ZgfK8GK5AXpCAbbCDzATv5pJKHBuCIt17BO__Ph-5xp3g6yFAZCn2DHJ20hA.jpg',
      icon: {
        src: 'https://cdn5.telesco.pe/file/JByt0C76yv8Y5j2CoJKhnGfhHzAunNJjjptxnKwpMZG5hDAG4LhrOki-KVe19zShiABm-n2AreKje38U0766QLPnNa2Mw-KRWtXuGwRqY7X3ttXCAHOA1BPEz8dXkFte7AiCc8QAhEqLP7RXqXfoRm5Sb9KpdZ4rI9t0CVSRd8OFnxQeIkoLCScwko4gTxqFu3FXL_ke2QAZdLRCDqjfDDxuTjHFM3DwMQRn778T11bX6FhisPVjmXtnxQJR9LTBDph1tgKVUP1y7fsXV50YBHOix6ZgfK8GK5AXpCAbbCDzATv5pJKHBuCIt17BO__Ph-5xp3g6yFAZCn2DHJ20hA.jpg',
        width: '100%',
      },
    },
    {
      title: 'Liet Blue (She/Her)',
      details:
        '前端',
      link: 'https://cdn5.telesco.pe/file/MMuZP7keN8agE_Dagf7ADD4wqLr2FKSsuXjaPQy8cJlQh0zd16eAQeX6suq3KsPNcQkNuxKLexoa5mlKaZoSBJEljwnuaFBBUBDuEm1qJhiVEqnx64FJtZY_mtFQhhHIcG-EuFp_dPk2ffwdXJVwgq2w7aSjV9MTCszcSxIN2I8N4RCWt6ml63c76nORXMJ_hVVGDcSOTygG0FtHY52B619fHLT_MXQA_ysQF5vh-D1KNzgVwEYEp6lOCUCys0fSEEtAZcRpQRd6zJddGP6O0MWCS93fAq1elhya535KBYHXomvpkH7w8Tf9yM1nyBHDUjIIkBMFKRu_8L95GkeaLg.jpg',
      icon: {
        src: 'https://cdn5.telesco.pe/file/MMuZP7keN8agE_Dagf7ADD4wqLr2FKSsuXjaPQy8cJlQh0zd16eAQeX6suq3KsPNcQkNuxKLexoa5mlKaZoSBJEljwnuaFBBUBDuEm1qJhiVEqnx64FJtZY_mtFQhhHIcG-EuFp_dPk2ffwdXJVwgq2w7aSjV9MTCszcSxIN2I8N4RCWt6ml63c76nORXMJ_hVVGDcSOTygG0FtHY52B619fHLT_MXQA_ysQF5vh-D1KNzgVwEYEp6lOCUCys0fSEEtAZcRpQRd6zJddGP6O0MWCS93fAq1elhya535KBYHXomvpkH7w8Tf9yM1nyBHDUjIIkBMFKRu_8L95GkeaLg.jpg',
        width: '100%',
      },
    },
  ],
};
</script>
