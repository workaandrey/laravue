<template>
  <el-dropdown trigger="click" class="international" @command="handleSetCurrency">
    <div>
      USD
    </div>
    <el-dropdown-menu slot="dropdown">
      <el-dropdown-item :disabled="language==='usd'" command="usd">
        USD
      </el-dropdown-item>
      <el-dropdown-item :disabled="language==='eur'" command="eur">
        EUR
      </el-dropdown-item>
    </el-dropdown-menu>
  </el-dropdown>
</template>

<script>
export default {
  computed: {
    language() {
      return this.$store.getters.language;
    },
  },
  methods: {
    handleSetCurrency(currency) {
      // this.$i18n.locale = lang;
      this.$store.dispatch('app/setCurrency', currency);
      this.$message({
        message: 'Switch Currency Success',
        type: 'success',
      });
    },
  },
};
</script>

<style scoped>
.international-icon {
  font-size: 20px;
  cursor: pointer;
  vertical-align: -5px!important;
}
</style>

