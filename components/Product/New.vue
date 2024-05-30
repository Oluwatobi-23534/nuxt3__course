<script setup lang="ts">
import {
  AlertDialog,
  AlertDialogAction,
  AlertDialogCancel,
  AlertDialogContent,
  AlertDialogDescription,
  AlertDialogFooter,
  AlertDialogHeader,
  AlertDialogTitle,
  AlertDialogTrigger,
} from "@/components/ui/alert-dialog";

const { loading, open } = useHelpers();

const createNewProduct = async () => {
  try {
    loading.value = true;
    // bussiness logic
  } catch (error) {
  } finally {
    loading.value = false;
    open.value = false;
  }
};
</script>

<template>
  <AlertDialog :open="open">
    <AlertDialogTrigger>
      <button @click="open = true"
        class="bg-gradient-to-r from-purple-500 to-pink-500 text-white font-bold py-2 px-4 rounded"
      >
        Add a new product
      </button>
    </AlertDialogTrigger>
    <AlertDialogContent>
      <AlertDialogHeader> 
        <AlertDialogTitle>Create a new product</AlertDialogTitle>
        <Input placeholder="Enter product name" />
      </AlertDialogHeader>
      <AlertDialogFooter>
        <AlertDialogCancel @click="open = false">Cancel</AlertDialogCancel>
        <AlertDialogAction @click="createNewProduct()"
          >Create</AlertDialogAction
        >
      </AlertDialogFooter>
    </AlertDialogContent>
  </AlertDialog>
</template>
