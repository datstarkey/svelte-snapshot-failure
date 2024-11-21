<script lang="ts">
    interface Props {
        name: string;
    };
    let {
        name
    }:Props = $props();
</script>

<p>{name}</p>