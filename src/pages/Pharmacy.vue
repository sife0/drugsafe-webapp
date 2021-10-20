<template>
  <el-container>
    <el-header></el-header>
    <el-main>
      <el-button type="primary" @click="dialogFormVisible = true">添加药店</el-button>
      <el-divider></el-divider>
      <el-table
        :data="pharmacyList"
        stripe
        style="width: 100%">
        <el-table-column
          prop="hospitalId"
          label="医院id">
        </el-table-column>
        <el-table-column
          prop="hospitalName"
          label="医院名">
        </el-table-column>
        <el-table-column
          prop="pharmacyId"
          label="药店id">
        </el-table-column>
        <el-table-column
          prop="pharmacyName"
          label="药店名">
        </el-table-column>
        <el-table-column
          prop="pharmacyContact"
          label="药店联系人">
        </el-table-column>
        <el-table-column
          prop="pharmacyTel"
          label="药店电话">
        </el-table-column>
        <el-table-column
          prop="pharmacyAddr"
          label="药店地址">
        </el-table-column>
        <el-table-column
          prop="pharmacyImg"
          label="药店图片地址">
        </el-table-column>
        <el-table-column
          prop="pharmacyDetail"
          label="药店描述">
        </el-table-column>
        <el-table-column label="操作">
          <template slot-scope="scope">
<!--            <el-button-->
<!--              size="mini"-->
<!--              @click="handleEdit(scope.$index, scope.row)">编辑</el-button>-->
            <el-button
              size="mini"
              type="danger"
              @click="handleDelete(scope.$index, scope.row)">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
    </el-main>
    <el-dialog title="添加药店" :visible.sync="dialogFormVisible">
      <el-form :model="form">
        <el-form-item label="医院id" :label-width="formLabelWidth">
          <el-input v-model="form.hospitalId"></el-input>
        </el-form-item>
        <el-form-item label="医院名" :label-width="formLabelWidth">
          <el-input v-model="form.hospitalName"></el-input>
        </el-form-item>
        <el-form-item label="药店id" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyId"></el-input>
        </el-form-item>
        <el-form-item label="药店名" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyName"></el-input>
        </el-form-item>
        <el-form-item label="药店联系人" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyContact"></el-input>
        </el-form-item>
        <el-form-item label="药店电话" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyTel"></el-input>
        </el-form-item>
        <el-form-item label="药店地址" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyAddr"></el-input>
        </el-form-item>
        <el-form-item label="药店图片地址" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyImg"></el-input>
        </el-form-item>
        <el-form-item label="药店描述" :label-width="formLabelWidth">
          <el-input v-model="form.pharmacyDetail"></el-input>
        </el-form-item>
      </el-form>
      <div slot="footer" class="dialog-footer">
        <el-button @click="dialogFormVisible = false">取 消</el-button>
        <el-button type="primary" @click="addPharmacy">确 定</el-button>
      </div>
    </el-dialog>
  </el-container>
</template>

<script>
export default {
  name: "pharmacy",
  data() {
    return {
      dialogFormVisible: false,
      formLabelWidth:'120px',
      form: {
        hospitalId:'',
        hospitalName: '',
        pharmacyId:'',
        pharmacyName:'',
        pharmacyImg:'',
        pharmacyTel:'',
        pharmacyAddr:'',
        pharmacyContact:'',
        pharmacyDetail:''
      },
      pharmacyList:[],
    }
  },
  methods: {
    handleEdit(index, row) {
      this.dialogFormVisible = true;
      this.form = row;
    },
    handleDelete(index, row) {
      console.log(index, row);
    },
    addPharmacy() {
      this.dialogFormVisible = false;
      this.pharmacyList.push(this.form);
    }
  }
}
</script>

<style scoped>

</style>
