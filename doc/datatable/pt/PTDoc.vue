<template>
    <DocSectionText v-bind="$attrs"></DocSectionText>
    <div class="card">
        <DataTable
            :value="products"
            sortMode="multiple"
            :pt="{
                table: { style: { minWidth: '50rem' } }
            }"
        >
            <Column
                field="code"
                header="Code"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="name"
                header="Name"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="category"
                header="Category"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="quantity"
                header="Quantity"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
        </DataTable>
    </div>
    <DocSectionCode :code="code" :service="['ProductService']" />
</template>

<script>
import { ProductService } from '@/service/ProductService';

export default {
    data() {
        return {
            products: null,
            code: {
                basic: `
<DataTable
    :value="products"
    sortMode="multiple"
    :pt="{
        table: { style: { minWidth: '50rem' } }
    }"
>
    <Column
        field="code"
        header="Code"
        sortable
        :pt="{
            sortBadge: { class: 'bg-primary' },
            headerCell: { style: { width: '25%' } }
        }"
    />
    <Column
        field="name"
        header="Name"
        sortable
        :pt="{
            sortBadge: { class: 'bg-primary' },
            headerCell: { style: { width: '25%' } }
        }"
    />
    <Column
        field="category"
        header="Category"
        sortable
        :pt="{
            sortBadge: { class: 'bg-primary' },
            headerCell: { style: { width: '25%' } }
        }"
    />
    <Column
        field="quantity"
        header="Quantity"
        sortable
        :pt="{
            sortBadge: { class: 'bg-primary' },
            headerCell: { style: { width: '25%' } }
        }"
    />
</DataTable>`,
                options: `
<template>
    <div class="card">
        <DataTable
            :value="products"
            sortMode="multiple"
            :pt="{
                table: { style: { minWidth: '50rem' } }
            }"
        >
            <Column
                field="code"
                header="Code"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="name"
                header="Name"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="category"
                header="Category"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="quantity"
                header="Quantity"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
        </DataTable>
    </div>
</template>

<script>
import { ProductService } from '@/service/ProductService';

export default {
    data() {
        return {
            products: null
        };
    },
    mounted() {
        ProductService.getProductsMini().then((data) => (this.products = data));
    }
};
<\/script>`,
                composition: `
<template>
    <div class="card">
        <DataTable
            :value="products"
            sortMode="multiple"
            :pt="{
                table: { style: { minWidth: '50rem' } }
            }"
        >
            <Column
                field="code"
                header="Code"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="name"
                header="Name"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="category"
                header="Category"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
            <Column
                field="quantity"
                header="Quantity"
                sortable
                :pt="{
                    sortBadge: { class: 'bg-primary' },
                    headerCell: { style: { width: '25%' } }
                }"
            />
        </DataTable>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { ProductService } from '@/service/ProductService';

onMounted(() => {
    ProductService.getProductsMini().then((data) => (products.value = data));
});

const products = ref();

<\/script>`,
                data: `
{
    id: '1000',
    code: 'f230fh0g3',
    name: 'Bamboo Watch',
    description: 'Product Description',
    image: 'bamboo-watch.jpg',
    price: 65,
    category: 'Accessories',
    quantity: 24,
    inventoryStatus: 'INSTOCK',
    rating: 5
},
...
        `
            }
        };
    },
    mounted() {
        ProductService.getProductsMini().then((data) => (this.products = data));
    }
};
</script>
