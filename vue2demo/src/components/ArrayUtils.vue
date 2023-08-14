<template>
  <div>
    测试utils
    <div>{{ processData }}</div>
  </div>
</template>
<script>
export default {
  name: "ArrayUtils",
  data() {
    return {
      arr: [
        {
          name: "test1",
          level: 0,
          status: 0,
        },
        {
          name: "test2",
          level: 0,
          status: 0,
          children: [
            {
              name: "test21",
              level: 1,
              status: 0,
            },
            {
              name: "test22",
              level: 1,
              status: 0,
            },
          ],
        },
        {
          name: "test3",
          level: 0,
          status: 0,
          children: [
            {
              name: "test31",
              level: 1,
              status: 0,
            },
            {
              name: "test32",
              level: 1,
              status: 1,
            },
            {
              name: "test33",
              level: 1,
              status: 2,
            },
          ],
        },
      ],
      processData: [],
    };
  },
  mounted() {
    this.processData = this.handleTagsTree(this.arr);
  },
  methods: {
    handleTagsTree(children) {
      const result = [];

      children.forEach((item) => {
        //如果存在children下一层，则递归遍历并赋值
        if (item?.children && item?.children.length) {
          item.children = this.handleTagsTree(item.children);
        }
        result.push(item);
      });
      return result.filter(
        (val) =>
          (val.level === 1 && val.status === 2) ||
          (val?.children && val.children.length)
      );
    },
  },
};
</script>
