<script lang="ts" module>
    // Define your toast data.
    type ToastData = {
      title: string;
      description: string;
    };
  
    const toaster = new Toaster<ToastData>();
  
    export const addToast = toaster.addToast;
  </script>
  
  <script lang="ts">
    import { Toaster } from "melt/builders";
  </script>
  
  <div class="m-4 gap-2 flex flex-col bg-opacity-0" {...toaster.root}>
    {#each toaster.toasts as toast (toast.id)}
  
      <div class="rounded bg-stone-50 border-stone-500 border-3 p-2" {...toast.content}>
        <h3 {...toast.title}>{toast.data.title}</h3>
        <div {...toast.description}>{toast.data.description}</div>
        <button class="cursor-pointer" {...toast.close} aria-label="dismiss alert">X</button>
      </div>
    {/each}
  </div>