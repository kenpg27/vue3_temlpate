<template>
    <div class="c-dialog">
        <transition name="dialog-fade" @after-enter="afterEnter" @after-leave="afterLeave">
            <c-overlay @click="overLayChange" :mask="overlaySwitch_Ref">
                <div ref="dialogRef">
                    {{ title }}
                </div>
            </c-overlay>
        </transition>
    </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import cOverlay from '@/components/c-overlay.vue'
export default defineComponent({
    name: 'c-dialog',
    components: {
        cOverlay
    },
    props: {
        title: {
            type: String,
            default: 'dialog-title'
        }
    },
    setup() {
        const overlaySwitch_Ref = ref(false)
        const overLayChange = () => {
            overlaySwitch_Ref.value = !overlaySwitch_Ref.value
        }
        const afterEnter = () => {}
        const afterLeave = () => {}

        return {
            overlaySwitch_Ref,
            overLayChange,
            afterEnter,
            afterLeave
        }
    }
})
</script>

<style lang="scss" scoped>
</style>
