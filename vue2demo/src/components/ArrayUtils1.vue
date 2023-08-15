<template>
    <div>
        
        <div>{{this.aaa}}</div>
        <hr>
   
    </div>
</template>
<script>
export default{
    data(){
        return {
            aaa:[
                {"id":"25","name":"测试","status":0,"level":3,"sub_trees":[
                    {"id":"25","name":"测试","status":0,"level":4},
                    {"id":"25","name":"测试","status":1,"level":4},
                    {"id":"25","name":"测试","status":2,"level":4}
                ]},
                {"id":"25","name":"测试","status":0,"level":3},
            ],
            bb:[]
        }
    },
    mounted(){
        this.bb = this.treeFilter(this.aaa, val => val.status === 2);
        console.log(this.bb)
    },
    methods:{
        treeFilter(tree, func) {
            // 使用map复制一下节点，避免修改到原树
            return tree
            .map(node => ({ ...node }))
            .filter(node => {
                node.sub_trees = node.sub_trees && this.treeFilter(node.sub_trees, func);
                return func(node) || (node.sub_trees && node.sub_trees.length);
            });
        },
    }
}
</script>
<style>
.top1{
    margin-left: 5px;
    color: aliceblue;
}
.top2{
    margin-left: 45px;
    color: blueviolet;
}
.top1{
    margin-left: 75px;
    color: blue;
}
.top2{
    margin-left: 105px;
    color: aqua;
}
</style>
