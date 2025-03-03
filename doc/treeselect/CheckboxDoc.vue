<template>
    <DocSectionText v-bind="$attrs">
        <p>Selection of multiple nodes via checkboxes is enabled by configuring <i>selectionMode</i> as <i>checkbox</i>.</p>
        <p>
            In checkbox selection mode, value binding should be a key-value pair where key is the node key and value is an object that has <i>checked</i> and <i>partialChecked</i> properties to represent the checked state of a node obje to indicate
            selection.
        </p>
    </DocSectionText>
    <DocSectionCode :code="activeNodes" hideToggleCode importCode hideCodeSandbox hideStackBlitz v-bind="$attrs" />
    <div class="card flex justify-content-center">
        <TreeSelect v-model="selectedValue" :options="nodes" selectionMode="checkbox" placeholder="Select Items" class="md:w-20rem w-full" />
    </div>
    <DocSectionCode :code="code" :service="['NodeService']" v-bind="$attrs" />
</template>

<script>
import { NodeService } from '/service/NodeService';

export default {
    data() {
        return {
            nodes: null,
            selectedValue: null,
            activeNodes: {
                basic: `
{
    '0-0': {
        partialChecked: false,
        checked: true
    }
}`
            },
            code: {
                basic: `
<TreeSelect v-model="selectedValue" :options="nodes" selectionMode="checkbox" placeholder="Select Item" class="md:w-20rem w-full" />`,
                options: `
<template>
    <div class="card flex justify-content-center">
        <TreeSelect v-model="selectedValue" :options="nodes" selectionMode="checkbox" placeholder="Select Item" class="md:w-20rem w-full" />
    </div>
</template>

<script>
import { NodeService } from './service/NodeService';

export default {
    data() {
        return {
            nodes: null,
            selectedValue: null,
        }
    },
    mounted() {
        NodeService.getTreeNodes().then((data) => (this.nodes = data));
    }
}
<\/script>`,
                composition: `
<template>
    <div class="card flex justify-content-center">
        <TreeSelect v-model="selectedValue" :options="nodes" selectionMode="checkbox" placeholder="Select Item" class="md:w-20rem w-full" />
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { NodeService } from './service/NodeService';

const nodes = ref(null);
const selectedValue = ref(null);

onMounted(() => {
    NodeService.getTreeNodes().then((data) => (nodes.value = data));
});
<\/script>`,
                data: `
{
    key: '0',
    label: 'Documents',
    data: 'Documents Folder',
    icon: 'pi pi-fw pi-inbox',
    children: [
        {
            key: '0-0',
            label: 'Work',
            data: 'Work Folder',
            icon: 'pi pi-fw pi-cog',
            children: [
                { key: '0-0-0', label: 'Expenses.doc', icon: 'pi pi-fw pi-file', data: 'Expenses Document' },
                { key: '0-0-1', label: 'Resume.doc', icon: 'pi pi-fw pi-file', data: 'Resume Document' }
            ]
        },
        {
            key: '0-1',
            label: 'Home',
            data: 'Home Folder',
            icon: 'pi pi-fw pi-home',
            children: [{ key: '0-1-0', label: 'Invoices.txt', icon: 'pi pi-fw pi-file', data: 'Invoices for this month' }]
        }
    ]
},
...`
            }
        };
    },
    mounted() {
        NodeService.getTreeNodes().then((data) => (this.nodes = data));
    }
};
</script>
