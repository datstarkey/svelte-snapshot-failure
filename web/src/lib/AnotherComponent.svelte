<script lang="ts">
interface Props {
    name: string;
};
let props:Props = $props();
</script>

<p>{props.name}</p>