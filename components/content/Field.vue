<template>
  <div class="[&:not(:first-child)]:mt-4 [&:not(:first-child)]:pt-4">
    <div class="flex mb-2 space-x-2">
      <span class="font-bold text-md text-primary">
        {{ name }}
      </span>
      <span v-if="required" class="self-center font-mono text-sm text-muted-foreground">
        required
      </span>
      <span class="flex-1" />
      <span class="self-center font-mono text-sm text-muted-foreground">
        {{ type }}
      </span>
    </div>
    <span class="text-sm text-muted-foreground">
      <ContentSlot unwrap="p" />
      {{ description }}
    </span>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  name: string;
  type?: string;
  required?: boolean;
  description?: string;
}>();
</script>
