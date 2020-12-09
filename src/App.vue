<template>
    <div class="app">
        <h4 class="app__title">{{ title }}</h4>
        <teleport to="body">
            <c-dialog></c-dialog>
        </teleport>
        <el-button type="text" @click="dialogVisible_Ref = true">点击打开 Dialog</el-button>

        <el-dialog title="提示" v-model="dialogVisible_Ref" width="30%" :before-close="handleClose">
            <span>这是一段信息</span>
            <template #footer>
                <span class="dialog-footer">
                    <el-button @click="dialogVisible_Ref = false">取 消</el-button>
                    <el-button type="primary" @click="dialogVisible_Ref = false">确 定</el-button>
                </span>
            </template>
        </el-dialog>
    </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import cDialog from '@/components/c-dialog.vue'
export default defineComponent({
    components: {
        cDialog
    },
    setup() {
        const title = 'vue3_cli_template'
        const dialogVisible_Ref = ref(false)
        const handleClose = () => {
            dialogVisible_Ref.value = false
        }
        return {
            title,
            dialogVisible_Ref,
            handleClose
        }
    }
})
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
.app {
    &__title {
        font-size: 26px;
    }
}
</style>
