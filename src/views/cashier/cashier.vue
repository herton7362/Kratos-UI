<style lang="less">
    @import "./cashier.less";
</style>
<template>
    <div class="cashier">
        <Row :gutter="8">
            <Col span="16">
                <Card :padding="0">
                    <Table :columns="saleList.columns" :height="500"></Table>
                </Card>
            </Col>
            <Col span="8">
                <Card :padding="0">
                    <Table :columns="productList.columns" :height="300"></Table>
                    <Button>会员</Button>
                    <Button type="error">结算</Button>
                </Card>
            </Col>
        </Row>
    </div>
</template>

<script>
    export default {
        name: 'cashier',
        data () {
            const saleListColumns = [
                {
                    title: '序号',
                    type: 'index',
                    width: 80,
                    align: 'center'
                },
                {
                    title: '品名',
                    key: 'name'
                },
                {
                    title: '数量',
                    width: 100,
                    key: 'count'
                },
                {
                    title: '单位',
                    width: 100,
                    key: 'unit'
                },
                {
                    title: '单价',
                    width: 100,
                    key: 'price'
                },
                {
                    title: '小计',
                    width: 100,
                    key: 'subtotal'
                }
            ];
            const productListColumns = [
                {
                    title: '编码',
                    key: 'code'
                },
                {
                    title: '品名',
                    key: 'name'
                },
                {
                    title: '单位',
                    width: 100,
                    key: 'unit'
                },
                {
                    title: '单价',
                    width: 100,
                    key: 'price'
                }
            ];
            return {
                saleList: {
                    columns: saleListColumns
                },
                productList: {
                    columns: productListColumns
                }
            };
        }
    };
</script>
