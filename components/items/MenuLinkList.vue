<template>
    <div>
        <div class="flex justify-between items-center">
            <nuxt-link :to="url" class="
                'w-56':showMenu,
                'w-16':!showMenu,
                'py-4':true,
                'transition-all':true,
                'duration-300':true,
                'ease-in-out':true,
                'focus:outline-none': true,
                'active:outline-none': true,
                "
                >
                <slot name="icon-word"></slot>
            </nuxt-link>
            <div class="px-2 py-4">
                <button @click="showList=!showList" class="focus:outline-none active:outline-none">
                    <i :class="{
                        'fas':true,
                        'hover:text-white':true,
                        'fa-sort-up':!showList,
                        'fa-sort-down':showList,
                        'hidden':!showMenu
                    }"></i>
                </button>
            </div>
        </div>
        <div :class="{
            'transition-all':true,
            'duration-300':true,
            'ease-in-out':true,
            'h-0':!showList,
            'py-4': showList,
            'bg-black': true,
            'overflow-hidden':true
            }">
            <slot name="sub-link"></slot>
        </div>
    </div>
</template>
<script>
import { mapState } from 'vuex'

export default {
    props:{
        url: String
    },
    computed:{
    ...mapState({
    showMenu: state => state.dashboard.showMenu
    })
},
    data(){
        return{
            showList: false
        }
    }
}
</script>