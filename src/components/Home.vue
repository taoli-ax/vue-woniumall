<template>


        <!-- <el-main>
        <el-scrollbar>
          <el-table :data="weather">
            <el-table-column  prop="date" label="Date" width="140" />
            <el-table-column  prop="name" label="Name" width="120" />
          </el-table>
          <el-table :data="holidays">
            <el-table-column  prop="date" label="Date" width="140" />
            <el-table-column  prop="name" label="Name" width="120" />
          </el-table>
        </el-scrollbar>
      </el-main>
        

        <div>
            <el-row >
            <el-col :span="10" class="" ><button @click="showWeather">展开/隐藏 24节气</button></el-col>
            <el-col :span="10" class=""><button @click="showHolidays">展开/隐藏 节日</button> </el-col>
             </el-row>
        </div>

        
        <div v-show="isActiveW">
            <h3>24节气</h3>
            <el-row  v-for="w in weather" :key="w.id">
                <el-col :span="5" class="col1" >{{w.name}}</el-col>
                <el-col :span="5" class="col2">{{w.date}} </el-col>
            </el-row>
        </div>
       <div v-show="isActiveH">
            <h3>传统节日</h3>
            <el-row  v-for="h in holidays" :key="h.id">
                <el-col :span="5" class="col1" >{{h.name}}</el-col>
                <el-col :span="10" class="col2">{{h.date}} </el-col>
            </el-row>

       </div>
         -->
    <el-container class="layout-container-demo" style="height: 1500px">
        <el-aside width="200px">
            <el-scrollbar>
                <el-menu :default-openeds="['1']">
                <el-sub-menu index="1">
                    <template #title>
                    <el-icon><message /></el-icon>背诵
                    </template>
                    <el-menu-item-group>
                    <template #title>2023 年 1 月</template>
                    <el-menu-item @click="showWeather" index="1-1">24节气</el-menu-item>
                    <el-menu-item @click="showHolidays" index="1-2">传统节日</el-menu-item>
                    </el-menu-item-group>
                
                </el-sub-menu>
                <!-- <el-sub-menu index="2">
                    <template #title>
                    <el-icon><icon-menu /></el-icon>Navigator Two
                    </template>
                    <el-menu-item-group>
                    <template #title>Group 1</template>
                    <el-menu-item index="2-1">Option 1</el-menu-item>
                    <el-menu-item index="2-2">Option 2</el-menu-item>
                    </el-menu-item-group>
                    <el-menu-item-group title="Group 2">
                    <el-menu-item index="2-3">Option 3</el-menu-item>
                    </el-menu-item-group>
                    <el-sub-menu index="2-4">
                    <template #title>Option 4</template>
                    <el-menu-item index="2-4-1">Option 4-1</el-menu-item>
                    </el-sub-menu>
                </el-sub-menu> -->
                </el-menu>
            </el-scrollbar>
        </el-aside>

        <el-container>
            <el-header style="text-align: right; font-size: 12px">
                <div class="toolbar">
                <el-dropdown>
                    <el-icon style="margin-right: 8px; margin-top: 1px"
                    ><setting
                    /></el-icon>
                    <template #dropdown>
                    <el-dropdown-menu>
                        <el-dropdown-item>View</el-dropdown-item>
                        <el-dropdown-item>Add</el-dropdown-item>
                        <el-dropdown-item>Delete</el-dropdown-item>
                    </el-dropdown-menu>
                    </template>
                </el-dropdown>
                <span>Tom</span>
                </div>
            </el-header>
            <el-container>
            <el-main v-show="isActiveW">
                <el-scrollbar>
                <el-table :data="weather">
                    
                    <el-table-column  prop="name" label="节气名" width="280" />
                    <el-table-column  prop="date" label="日期" width="380" />
                </el-table>
                
                </el-scrollbar>
            </el-main>
            <el-main v-show="isActiveH">
                <el-scrollbar>
                <el-table :data="holidays">
                    
                    <el-table-column   prop="name" label="节日名称" width="280" />
                    <el-table-column   prop="date" label="农历" width="380" />
                </el-table>
                </el-scrollbar>
            </el-main>
        </el-container>
            
        
        </el-container>
    </el-container>
  
    

</template>
      



<script>
import { Menu as IconMenu, Message, Setting } from '@element-plus/icons-vue'
export default {
    data(){
        return{
            isActiveW:false,
            isActiveH:false,
            weather:[
                {"id":"1","name":"立春","date":"2.3"},
                {"id":"2","name":"雨水","date":"2.18"},
                {"id":"3","name":"惊蛰","date":"3.5"},
                {"id":"4","name":"春分","date":"3.20"},
                {"id":"5","name":"清明","date":"4.4"},
                {"id":"6","name":"谷雨","date":"4.19"},
                {"id":"7","name":"立夏","date":"5.5"},
                {"id":"8","name":"小满","date":"5.20"},
                {"id":"9","name":"芒种","date":"6.5"},
                {"id":"10","name":"夏至","date":"6.21"},
                {"id":"11","name":"小暑","date":"7.6"},
                {"id":"12","name":"大暑","date":"7.22"},
                {"id":"13","name":"立秋","date":"8.7"},
                {"id":"14","name":"处暑","date":"8.22"},
                {"id":"15","name":"白露","date":"9.7"},
                {"id":"16","name":"秋分","date":"9.22"},
                {"id":"17","name":"寒露","date":"10.8-9"},
                {"id":"18","name":"霜降","date":"10.23-24"},
                {"id":"19","name":"立冬","date":"11.7-8"},
                {"id":"20","name":"小雪","date":"11.22-23"},
                {"id":"21","name":"大雪","date":"12.6"},
                {"id":"22","name":"冬至","date":"12.21"},
                {"id":"23","name":"小寒","date":"1.5"},
                {"id":"24","name":"大寒","date":"1.20-21"},
            ],
            holidays:[
                {"id":"1","name":"春节","date":"正月初一"},
                {"id":"2","name":"元宵节","date":"正月十五"},
                {"id":"3","name":"龙抬头","date":"二月初二"},
                {"id":"4","name":"社日节","date":"二月初二"},
                {"id":"5","name":"上已节","date":"三月初三"},
                {"id":"6","name":"寒食节","date":"冬至后105/106天\，清明节前一两天"},
                {"id":"7","name":"清明节","date":"4.5"},
                {"id":"8","name":"端午节","date":"五月初五"},
                {"id":"9","name":"七夕节","date":"七月初七"},
                {"id":"10","name":"中元节","date":"七月十五"},
                {"id":"11","name":"中秋节","date":"八月十五"},
                {"id":"12","name":"重阳节","date":"九月初九"},
                {"id":"13","name":"寒衣节","date":"十月初一"},
                {"id":"14","name":"下元节","date":"十月十五"},
                {"id":"15","name":"冬至节","date":"12.21"},
                {"id":"16","name":"腊八节","date":"腊月初八"},
                {"id":"17","name":"小年","date":"腊月二十三"},
                {"id":"18","name":"除夕","date":"腊月最后一天"},
            ]
        }
    },
    methods:{
        showWeather(){
            this.isActiveW=!this.isActiveW;
        },
        showHolidays(){
            this.isActiveH=!this.isActiveH;
        }
    }
}
</script>

<style scoped>
.layout-container-demo .el-header {
  position: relative;
  background-color: var(--el-color-primary-light-7);
  color: var(--el-text-color-primary);
}
.layout-container-demo .el-aside {
  color: var(--el-text-color-primary);
  background: var(--el-color-primary-light-8);
}

.layout-container-demo .el-menu {
  border-right: none;
}

.home{
    font-family: '微软雅黑';
    
}
.col1{
    background-color:  #2a598a;
    color: aliceblue;
    
}
.col2{
    background-color:   #3375b9;
    color: aliceblue;
}
</style>