<template>
    <div class="row">
        <survey-section />
        <slider-section1 />
        <slider-section2 />
        <slider-section3 />
        
    </div>
</template>

<script>
import SurveySection from '@/components/survey/SurveySection.vue';
import SliderSection1 from '@/components/section/SliderSection1.vue';
import SliderSection2 from '@/components/section/SliderSection2.vue';
import SliderSection3 from '@/components/section/SliderSection3.vue';

    export default {
        components:{
            SurveySection,
            SliderSection1,
            SliderSection2,
            SliderSection3,
           
        }
    }
</script>

<style lang="scss" scoped>

</style>