<template>
    
    <div class = "flex flex-col">
        <contentCard class="mt-2 mb-4">
            <template v-slot:title>
                Sales Statistic
            </template>
            <template v-slot:content>
                <div class="w-full overflow-hidden p-2">
                <barChart :chartData="revenueMonthly.barChartData"
            :options="revenueMonthly.barChartOptions" :height="120"></barChart>
                </div>
            </template>
        </contentCard>
    </div>
</template>
    
<script>
    import ContentCard from "~/components/items/ContentCard.vue";
    import BarChart from "~/components/charts/BarChart";
    import LineChart from "~/components/charts/LineChart";

    const chartColors = {
        red:'rgb(255,99,132)',
        orange:'rgb(255,159,64)',
        yellow:'rgb(255,205,86)',
        green:'rgb(75,192,192)',
        blue:'rgb(54,162,1235)',
        purple:'rgb(153,102,255)',
        grey:'rgb(201,203,207)',
    };


    export default {
        transition:{
        name:"inventory",
        mode:"out-in",
        duration:{enter:1000, leave:500},
        enterActiveClass:"animated fadeIn",
        leaveActiveClass:"animated fadeOut"
    },
        
        layout:"dashboard",
        components:{
            ContentCard,
            BarChart,
            LineChart
        },
        data(){
            return{
                revenueMonthly:{
                    barChartData:{
                        labels:['Jan','Feb','March','April','May'],
                        datasets: [
                            {
                                label: 'Income',
                                backgroundColor:[
                                    chartColors.green,
                                    chartColors.green,
                                    chartColors.green,
                                    chartColors.green,
                                    chartColors.green],

                                data:[5,3,4,2,4]                                                          
                            }
                        ],
                    },
                    barChartOptions:{
                        responsive: true,
                        legend:{
                            display: false,
                        },
                        title:{
                            display:true,
                            text: "Monthly Income"
                        },
                        scales:{
                            yAxes:[
                                {
                                    ticks:{
                                        beginAtZero: true,
                                        suggestMax: 10
                                    }
                                }
                            ]
                        }
    
                        
                    }
                }
            }
        }
    }
</script>