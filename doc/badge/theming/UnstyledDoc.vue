<template>
    <DocSectionText v-bind="$attrs">
        <p>Theming is implemented with the pass through properties in unstyled mode. Example below demonstrates the built-in Tailwind theme.</p>
    </DocSectionText>
    <DocSectionCode :code="code" embedded />
</template>

<script>
export default {
    data() {
        return {
            code: {
                composition: `
<template>
    <div class="card flex flex-wrap justify-content-center gap-2">
        <Badge value="2"></Badge>
        <Badge value="8" severity="success"></Badge>
        <Badge value="4" severity="info"></Badge>
        <Badge value="12" severity="warning"></Badge>
        <Badge value="3" severity="danger"></Badge>
    </div>
</template>

<script setup>

<\/script>`
            }
        };
    }
};
</script>
