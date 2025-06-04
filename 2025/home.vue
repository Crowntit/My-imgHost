<template>
    <!-- 推荐社团 -->
    <el-row style="margin-top: 10px;">
        <el-col :span="24">
            <el-card class="box-card" >
                <template #header>
                <div class="card-header">
                    <span class="moretitle">推荐社团</span>
                    <el-button class="button" text>更多
                        <el-icon>
                            <ArrowRight></ArrowRight>
                        </el-icon>
                    </el-button>
                </div>
                </template>
                <div>
                    <swipper1></swipper1>
                </div>
            </el-card>
        </el-col>
    </el-row>
    <!-- 活动推荐 + 系统公告-->
     <el-row :gutter="15" style="margin-top: 20px;">
        <el-col :span="8" :offset="0">
            <el-card class="box-card" >
                <template #header>
                <div class="card-header">
                    <span class="moretitle">推荐活动</span>
                    <el-button class="button" text>更多
                        <el-icon>
                            <ArrowRight></ArrowRight>
                        </el-icon>
                    </el-button>
                </div>
                </template>
                <div >
                    <swipper></swipper>
                </div>
            </el-card>
        </el-col>
        <el-col :span="16" :offset="0">
            <el-card class="box-card" >
                <template #header>
                <div class="card-header">
                    <span class="moretitle">系统公告</span>
                    <el-button class="button" text>更多
                        <el-icon>
                            <ArrowRight></ArrowRight>
                        </el-icon>
                    </el-button>
                </div>
                </template>
                <div >
                    <div v-for="(item,index) in noticeList" class="notice">
                        <div class="title">{{ index+1 +"、"+item.title }}</div>
                         <div class="date">{{ item.createTime }}</div>
                    </div>
                </div>
            </el-card>
        </el-col>
     </el-row>
     <!-- 最新活动 -->
     <!-- <el-row style="margin-top: 20px;">
        <el-col :span="24" :offset="0">
            <el-card class="box-card" >
                <template #header>
                <div class="card-header">
                    <span class="moretitle">最新活动</span>
                    <el-button class="button" text>更多
                        <el-icon>
                            <ArrowRight></ArrowRight>
                        </el-icon>
                    </el-button>
                </div>
                </template>
                <div >
                    <div v-for="(item,index) in noticeList" class="notice">
                        <div class="title">{{ index+1 +"、"+item.title }}</div>
                         <div class="date">{{ item.createTime }}</div>
                    </div>
                </div>
            </el-card>
        </el-col>
     </el-row> -->
     <el-row :gutter="20" style="margin-top: 20px;">
        <el-col :span="6" v-for="(item, index) in activities" :key="index">
            <el-card shadow="hover">
                <img :src="item.image" class="activities-img" />
                <h3>{{ item.name }}</h3>
                <p>{{ item.description }}</p>
                <el-button type="primary">查看详情</el-button>
            </el-card>
        </el-col>
    </el-row>
</template>

<script setup lang="ts">
import {ref} from 'vue'

import img5 from "@/assets/act1.png";
import img6 from "@/assets/act2.png";
import img7 from "@/assets/act3.png";
import img8 from "@/assets/act4.png";

import swipper1 from './swipper1.vue';
import swipper from './swipper.vue';
import Activity from '../activity/activity.vue';

const noticeList = ref([
    {
        title:'篮球社最新招新公告',
        createTime:'2025-01-20'
    },
    {
        title:'羽毛球社最新招新公告',
        createTime:'2025-03-01'
    },
    {
        title:'气排球社最新招新公告',
        createTime:'2025-05-10'
    },
    {
        title:'足球社最新招新公告',
        createTime:'2025-03-11'
    },
    {
        title:'书法社最新招新公告',
        createTime:'2025-02-26'
    },
    {
        title:'音乐社最新招新公告',
        createTime:'2025-04-10'
    },
    {
        title:'数学社最新招新公告',
        createTime:'2025-02-10'
    },
    {
        title:'物理社最新招新公告',
        createTime:'2025-02-10'
    },
    {
        title:'滑轮社最新招新公告',
        createTime:'2025-02-10'
    },
    {
        title:'古风社最新招新公告',
        createTime:'2025-02-10'
    },
]);

const activities = ref([
  { name: "📌525心理健康活动", image: img5, description: "旨在缓解学生压力，积极面对生活" },
  { name: "🎨创意市集日", image: img6, description: "展示学生原创手工艺品，释放无限灵感" },
  { name: "🏃 阳光晨跑挑战", image: img7, description: "鼓励学生每天清晨跑步，唤醒活力新一天" },
  { name: "🎭校园剧场夜", image: img8, description: "学生自编自导舞台剧，展现青春与才华" },
]);
</script>

<style scoped lang="scss">
.card-header{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.text{
    font-size: 14px;
}
.item{
    margin-bottom: 18px;
}
.moretitle{
    color: #F3AF28;
    font-weight: 600;
}
.notice{
    cursor: pointer;
    display: flex;
    height: 30px;
    line-height: 30px;
    .title{
        font-size: 14px;
        font-weight: 600;
        color: #666666;
    }
    .date{
        font-size: 14px;
        margin-left: 20px;
    }
}
.activities-img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  
}
</style>