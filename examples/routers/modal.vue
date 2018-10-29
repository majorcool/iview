<template>
    <div>
        <Button @click="instance('info')">Info</Button>
        <Button @click="instance('success')">Success</Button>
        <Button @click="instance('warning')">Warning</Button>
        <Button @click="instance('error')">Error</Button>
        <Button @click="open">draggable</Button>
        <Modal v-model="visible"
               draggable
               :width="80">
            <header slot="header">
                风飒风蛋糕辅导班粉红色
            </header>
        </Modal>
    </div>
</template>

<script>
import Modal from "../../src/components/modal";
console.log("Modal", Modal);
export default {
  data() {
    return { visible: false };
  },
  methods: {
    open() {
      this.visible = true;
    },
    instance(type) {
      const title = "Title";
      const content = "<p>Content of dialog</p><p>Content of dialog</p>";
      switch (type) {
        case "info":
          this.$Modal.info({
            title: title,
            content: content,
          });
          break;
        case "success":
          this.$Modal.success({
            title: title,
            content: content,
          });
          break;
        case "warning":
          this.$Modal.warning({
            title: title,
            content: content,
          });
          break;
        case "error":
          this.$Modal.error({
            title: title,
            content: content,
          });
          break;
      }
    },
  },
};
</script>
