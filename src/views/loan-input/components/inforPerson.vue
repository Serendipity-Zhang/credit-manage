<!-- 个人信息-->
<template>
  <div class=''>
     <el-form ref="temp" :rules="rules" :model="temp" label-position="left" label-width="80px" >
     <el-card class="box-card">
       <!-- <div slot="header" class="clearfix">
         <span>个人基本信息</span>
       </div> -->
     <el-row :gutter="10">
        <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="姓名" prop="name">
                <el-input v-model="temp.name" />
              </el-form-item>
            </el-col>
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="出生日期" prop="birthday">
                <el-date-picker type="datetime" v-model="temp.birthday" />
              </el-form-item>
            </el-col>
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="性别" prop="sex">
                <el-select v-model="temp.sex" class="filter-item" placeholder="Please select">
                  <el-option v-for="item in sexOptions" :key="item.key" 
                    :label="item.display_name" :value="item.key" />
                </el-select>
              </el-form-item>
            </el-col>
          </el-row>

            <el-row :gutter="10">
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="身份证" prop="identity_card">
                <el-input v-model.number="temp.identity_card" />
              </el-form-item>
            </el-col>
          </el-row>

          <el-row :gutter="10">
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="婚姻状态" prop="marriage">
                <el-select v-model="temp.marriage" class="filter-item" placeholder="Please select">
                  <el-option v-for="item in marriageOptions" :key="item.key" :label="item.display_name" :value="item.key" />
                </el-select>
              </el-form-item>
            </el-col>
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="教育程度" prop="education">
                <el-select v-model="temp.education" class="filter-item" placeholder="Please select">
                  <el-option v-for="item in educationOptions" :key="item.key" :label="item.display_name" :value="item.key" />
                </el-select>
              </el-form-item>
            </el-col>
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="居住地址" prop="address1">
                <el-input v-model="temp.address1" />
              </el-form-item>
            </el-col>
          </el-row>
          
          <el-row :gutter="10">
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="户籍地址" prop="address2">
                <el-input v-model="temp.address2" />
              </el-form-item>
            </el-col>
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="居住电话" prop="phone">
                <el-input v-model.number="temp.phone" />
              </el-form-item>
            </el-col>
            <el-col :xs="24" :sm="12" :md="8" :lg="8">
              <el-form-item label="手机号" prop="mobile_phone">
                <el-input v-model.number="temp.mobile_phone" />
              </el-form-item>
            </el-col>
          </el-row>
        
          
     </el-card>
     </el-form>
  </div>
</template>

<script>
  //import x from ''
  export default {
    name:'inforPerson',
    components: {

    },
    data() {
    return {
      temp:{
        name:'',//姓名
        identity_card:'',//身份证
        birthday:'',//出生日期
        sex:'',//性别
        marriage:'',//婚姻状态
        education:'',//教育程度
        address1:'',//居住地址
        address2:'',//户籍地址
        phone:'',//居住电话
        mobile_phone:'',//手机号
        company:'',//现职公司全称
        trade:'',//所属行业
        position:'',//职位
        address3:'',//公司地址
        company_type:'',//公司类型
        company_email:'',//公司邮箱
        company_phone:'',//公司电话
        income:'',//收支情况
        contact:'',//关系1
        contact_name:'',//姓名
        contact_phone:'',//手机
        contact2:'',//关系2
        contact2_name:'',//姓名
        contact2_phone:'',//手机
        ontact2_dep:'',//部门
        contact2_pos:'',//职位
        remark:''//备注
      },
      rules: {
          name: [
            { required: true, message: '请输入姓名', trigger: 'blur' },
            { min: 2, max: 5, message: '长度在 2 到 5 个字符', trigger: 'blur' }
          ],
          identity_card: [
            { required: true, message: '请输入身份证', trigger: 'change' }
          ],
          birthday: [
            { type: 'date', required: true, message: '请选择日期', trigger: 'change' }
          ],
          sex: [
            { required: true, message: '请选择性别', trigger: 'change' }
          ],
          marriage: [
            { required: true, message: '请选择婚姻状态', trigger: 'change' }
          ],
          education: [
            { required: true, message: '请选择教育程度', trigger: 'change' }
          ],
          trade: [
            { required: true, message: '请选择所属行业', trigger: 'change' }
          ],

          address1: [
            { required: true, message: '请输入居住地址', trigger: 'blur' }
          ],
          address2: [
            { required: true, message: '请输入户籍地址', trigger: 'blur' }
          ],
          phone: [
            { required: true, message: '请输入居住电话', trigger: 'blur' }
          ],
          mobile_phone: [
            { required: true, message: '请输入手机号', trigger: 'blur' }
          ],
          company: [
            { required: true, message: '请输入现职公司全称', trigger: 'blur' }
          ],
          position:[
            { required: true, message: '请输入职位', trigger: 'blur' }
          ],
          address3:[
            { required: true, message: '请输入公司地址', trigger: 'blur' }
          ],
          company_type:[
            { required: true, message: '请输入公司类型', trigger: 'blur' }
          ],
          company_email:[
            { required: true, message: '请输入公司邮箱', trigger: 'blur' }
          ],
          company_phone:[
            { required: true, message: '请输入公司电话', trigger: 'blur' }
          ],
          income:[
            { required: true, message: '请输入收支情况', trigger: 'blur' }
          ],
          contact:[
            { required: true, message: '请输入关系1', trigger: 'blur' }
          ],
          contact_name:[
            { required: true, message: '请输入姓名', trigger: 'blur' }
          ],
          contact_phone:[
            { required: true, message: '请输入手机', trigger: 'blur' }
          ],
          contact2:[
            { required: true, message: '请输入关系2', trigger: 'blur' }
          ],
          contact2_name:[
            { required: true, message: '请输入姓名', trigger: 'blur' }
          ],
          contact2_phone:[
            { required: true, message: '请输入手机', trigger: 'blur' }
          ],
          contact2_dep:[
            { required: true, message: '请输入部门', trigger: 'blur' }
          ],
          contact2_pos:[
            { required: true, message: '请输入职位', trigger: 'blur' }
          ]
        },
        sexOptions:[]
      //listLoading: true,
      // sexOptions,
      // companyOptions,
      // marriageOptions,
      // educationOptions
    }
  },
    computed: {

    },
    methods: {

    },
mounted() {

},
beforeCreate() {}, //生命周期 - 创建之前
beforeMount() {}, //生命周期 - 挂载之前
beforeUpdate() {}, //生命周期 - 更新之前
updated() {}, //生命周期 - 更新之后
beforeDestroy() {}, //生命周期 - 销毁之前
destroyed() {}, //生命周期 - 销毁完成
activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发
  }
</script>

<style>
</style>