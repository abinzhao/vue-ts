<template>
       
    <h1>测试 vueUse 的鼠标坐标</h1>
       
    <h3>Mouse: {{ x }} x {{ y }}</h3>
     
</template>

 
<script lang="ts">
import { defineComponent } from 'vue';
import { useMouse } from '@vueuse/core';
import request from '@/utils/axios';
import API from '@/api';

export default defineComponent({
    name: 'VueUse',
    setup() {
        const { x, y } = useMouse();

        return {
            x,
            y,
        };
    },
});

const requestRes = async () => {
    let result = await request({
        url: '/api/xxx',
        method: 'get',
    });
    console.log(result);
};

const requestRes = async () => {
    let result = await API.login('zhangsan', '123456');
    console.log(result);
};

console.log(requestRes);
</script>
