<template>
    <div class="whitPaper">
        <PageHeader :isShowRight="false"></PageHeader>
        <div class="whitPaper-pdf">
            <pdf src="/SLTWhitePaper.pdf"
                 class="pdfClass"
                 v-for="i in numPages"
                 :key="i"
                 :page="i"></pdf>
        </div>

    </div>
</template>

<script>
import Pdf from 'vue-pdf'
import PageHeader from "@/components/mobileComponents/comm/header";

export default {
    name: "whitPaper",
    components: {PageHeader, Pdf},
    data() {
        return {
            numPages: 37  //  pdf 文件总页数
        }
    }
}
</script>

<style scoped lang="less">
.whitPaper {
    .whitPaper-header {

    }

    .whitPaper-pdf {
        padding-top: 75rem;
        width: 100%;
        margin: 0 auto;

        .pdfClass {
            width: 100%;
            height: 100%;
        }

    }
}
</style>