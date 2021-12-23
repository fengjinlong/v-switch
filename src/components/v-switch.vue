<script lang="js">
import { defineComponent } from "vue";

export default defineComponent({
  name: "v-switch",
  props: ["case"],
  setup(props, { slots }) {
    return () => {
      if (slots[props.case]) {
        return slots[props.case] && slots[props.case]();
      }
      if (slots["default"]) {
        return slots["default"]();
      }
    };
  },
});
</script>
