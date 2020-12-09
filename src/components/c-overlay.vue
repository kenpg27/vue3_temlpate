<script lang="ts">
import { createVNode, defineComponent, renderSlot } from 'vue'
export default defineComponent({
    name: 'c-overlay',
    props: {
        mask: {
            type: Boolean,
            default: true
        },
        overlayClass: {
            type: String
        },
        zIndex: {
            type: Number
        }
    },
    emits: ['click'],
    setup(props, { slots, emit }) {
        const onMaskClick = () => {
            emit('click')
        }
        // init here
        return () => {
            return props.mask
                ? createVNode(
                      'div',
                      {
                          class: ['el-overlay', props.overlayClass],
                          style: {
                              zIndex: props.zIndex
                          },
                          onClick: onMaskClick
                      },
                      [renderSlot(slots, 'default')],
                      1,
                      ['onClick']
                  )
                : renderSlot(slots, 'default')
        }
    }
})
</script>

<style>
</style>