<style lang="less">
</style>

<template>
    <Form label-position="left" :label-width="labelWidth" inline>
        <FormItem label="user" style="width: 30%">
            <Input type="text" placeholder="Username">
            </Input>
        </FormItem>
        <FormItem label="password" style="width: 30%">
            <Input type="password" placeholder="Password">
            </Input>
        </FormItem>
        <FormItem style="width: 30%">
            <Button type="primary">查询</Button>
            <Button type="ghost">重置</Button>
            <Button type="text">展开 <Icon type="chevron-down"></Icon></Button>
        </FormItem>
    </Form>
</template>

<script>
    export default {
        name: 'table-search-form',
        props: {
            fields: Array,
            labelWidth: {
                type: Number,
                default: 80
            }
        },
        data() {
            return {
            }
        }
    };
</script>