<template>
    <div class="flex flex-col">
    <contentCard class="mt-2 mb-4">
<template v-slot:title>
    SALES STATISTICS
</template>
<template v-slot:content>
    <div class="w-full overflow-hidden p-2">
    <barChart :chartdata="
    revenueMonthly.barChartData"
    :options="revenueMonthly.barChartOptions" :height="120"></barChart>
    </div>
</template>
</contentCard>
</div>
</template>