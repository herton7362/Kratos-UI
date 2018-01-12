<style lang="less">
    @import '../../styles/common.less';
</style>

<template>
    <Card>
        <table-search-form></table-search-form>
        <table-operator></table-operator>
        <Row class="margin-top-16">
            <Table border :columns="columns" :data="data"></Table>
        </Row>
    </Card>
</template>

<script>
import data from './data/data';
import tableSearchForm from '../my-components/table-extention/table-search-form.vue';
import tableOperator from '../my-components/table-extention/table-operator.vue';

export default {
    name: 'page',
    components: {
        tableSearchForm,
        tableOperator
    },
    data() {
        return {
            columns: [
                {
                    title: 'Name',
                    key: 'name',
                    render: (h, params) => {
                        return h('div', [
                            h('Icon', {
                                props: {
                                    type: 'person'
                                }
                            }),
                            h('strong', params.row.name)
                        ]);
                    }
                },
                {
                    title: 'Age',
                    key: 'age'
                },
                {
                    title: 'Address',
                    key: 'address'
                },
                {
                    title: 'Action',
                    key: 'action',
                    width: 150,
                    align: 'center',
                    render: (h, params) => {
                        return h('div', [
                            h('Button', {
                                props: {
                                    type: 'primary',
                                    size: 'small'
                                },
                                style: {
                                    marginRight: '5px'
                                },
                                on: {
                                    click: () => {
                                        this.show(params.index)
                                    }
                                }
                            }, 'View'),
                            h('Button', {
                                props: {
                                    type: 'error',
                                    size: 'small'
                                },
                                on: {
                                    click: () => {
                                        this.remove(params.index)
                                    }
                                }
                            }, 'Delete')
                        ]);
                    }
                }
            ],
            data: data
        }
    },
    methods: {
        show (index) {
            this.$Modal.info({
                title: 'User Info',
                content: `Name：${this.data[index].name}<br>Age：${this.data[index].age}<br>Address：${this.data[index].address}`
            })
        },
        remove (index) {
            this.data.splice(index, 1);
        }
    }
};
</script>