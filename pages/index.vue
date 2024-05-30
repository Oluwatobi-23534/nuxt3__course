<script setup>
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";
const loading = ref(false);
let data = ref([]);

const list = [
  {
    title: "Today",
    component: resolveComponent("TabsToday"), // custom component relative to today
  },
  {
    title: "Week",
    component: "<div>today</div>",
  },
  {
    title: "Month",
    component: "<div>today</div>",
  },
  {
    title: "Year",
    component: "<div>today</div>",
  },
];


let currentCategory = ref("today");


function generateRandomData(number = 7) {
  let values = [];
  for (let i = 0; i < number + 1; i++) {
    values.push(Math.floor(Math.random() * 100));
  }

  data.value = values;
  return values;
}

const setCategory = (e) => {
  let v = e.target.innerText.toLowerCase();
  currentCategory.value = v;
  switch (v) {
    case "today":
      generateRandomData(24);
    case "week":
      generateRandomData(7);
    case "month":
      generateRandomData(31);
    case "year":
      generateRandomData(12);
  }
};

const cards = [
  {
    title: 'Sales',
    progression: 12,
    amount: 1244.74,
    label: 'View sales',
    description: 'Sales of May 2024',
    icon: 'solar:ticket-sale-outline'
  },
  {
    title: 'Refunds',
    progression: 8,
    amount: 84.44,
    label: 'View refunds',
    description: 'Refunds since the beginning of the year',
    icon: 'heroicons-outline:receipt-refund'
  },
  {
    title: 'Payouts',
    progression: 12,
    amount: 899.99,
    label: 'View payouts',
    description: 'Payouts of this week',
    icon: 'tabler:zoom-money'
  },
]

onMounted(() => {
  generateRandomData(24);
});



</script>

<template>
  <div class="grid gap-4 w-full">
    <header class="item-start flex justify-between">
      <div class="grow">
        <p>Hi, welcome back Dan !</p>
        <h1>Dashboard</h1>
      </div>
      <ProductNew/>
    </header>

    <main class="grid gap-4 w-full">
      <Tabs default-value="Today" class="w-full" @click="setCategory">
        <TabsList class="max-w-[400px]">
          <TabsTrigger
            v-for="(item, index) in list"
            :key="index"
            :value="item.title"
          >
            {{ item.title }}
          </TabsTrigger>
        </TabsList>
        <TabsContent class="w-[100%]"
          v-for="(item, index) in list"
          :key="index"
          :value="item.title"
        >
          <Chart v-if="data.length > 0" :currentCategory="currentCategory" :data="data"/>
        </TabsContent>
      </Tabs>
    </main>
    <footer>
      <div class="grid lg:grid-cols-3 gap-4">
        <Card
          v-for="(item, index) in cards"
          :key="index" :card="item"
        ></Card>
      </div>
    </footer>
  </div>
</template>
