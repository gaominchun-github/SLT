<template>
    <div class="positionRecord">
        <div class="positionRecord-content">
            <div class="positionRecord-item">
                <div class="title">
                    <div class="name">
                        {{ recordItem.title }}
                    </div>
                    <div class="detail">
                        {{ $t('positionRecord.detail') }}
                    </div>
                </div>
                <div class="content">
                    <table class="table">
                        <tr class="table-title">
                            <th class="time"> {{ $t('positionRecord.time') }}</th>
                            <th class="type"> {{ $t('positionRecord.type') }}</th>
                            <th class="number"> {{ $t('positionRecord.number') }}</th>
                            <th class="price"> {{ $t('positionRecord.price') }}</th>
                        </tr>
                        <tr class="table-data">
                            <th>{{ recordItem.time }}</th>
                            <th>{{ recordItem.type }}</th>
                            <th>{{ recordItem.number }}</th>
                            <th>{{ recordItem.price }}</th>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "positionRecord",
    data() {
        return {}
    },
    props: {
        recordItem:{
            type: Object,
            default: ()=>{

            }
        }
    },
    methods: {},
}
</script>

<style scoped lang="less">
.positionRecord {
    width: 100%;

    .positionRecord-content {
        .positionRecord-item {
            border: 1rem solid #E4E7ED;
            text-align: left;

            .title {
                width: 100%;
                height: 72rem;
                display: flex;
                align-items: center;
                justify-content: space-between;
                box-sizing: border-box;
                padding: 0 26rem;
                background: #F8FAFC;
                border-bottom: 1rem solid #E4E7ED;

                .name {
                    font-size: 30rem;
                    font-weight: bold;
                    color: #444444;
                }

                .detail {
                    font-size: 28rem;
                    font-weight: bold;
                    color: #22BF7C;
                }
            }

            .content {
                padding: 30rem 25rem;
                width: 100%;
                height: 133rem;
                background: #FFFFFF;
                box-sizing: border-box;

                table {
                    width: 100%;

                    .table-title {
                        font-size: 24rem;
                        font-weight: 400;
                        color: #9AA5B5;

                        .time {
                            width: 300rem;
                        }

                        .type {
                            width: 190rem;
                        }

                        .number {
                            width: 186rem;
                        }

                        .price {

                        }

                    }

                    .table-data {
                        //margin-top: 25rem;
                        height: 70rem;
                        font-size: 28rem;
                        font-weight: 400;
                        color: #444444;
                    }
                }
            }
        }
    }
}
</style>