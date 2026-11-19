<script setup lang="ts">
import { computed } from "vue";

const props = defineProps<{ name: string }>();
const icons = import.meta.glob<string>("../assets/tech-icons/*.svg", {
  eager: true,
  query: "?url",
  import: "default",
});
const slugs: Record<string, string> = {
  macOS: "apple", Linux: "linux", LineageOS: "lineageos", Windows: "windows",
  WezTerm: "wezterm", Zsh: "zsh", Git: "git", GitHub: "github", Arc: "arc",
  Google: "google", Neovim: "neovim", Vim: "vim", "Visual Studio Code": "editor",
  C: "c", "C++": "cplusplus", Rust: "rust", Python: "python",
  JavaScript: "javascript", TypeScript: "typescript", Scala: "scala",
  HTML: "html5", CSS: "css", LaTeX: "latex", Verilog: "hardware",
  SystemVerilog: "hardware", Chisel: "scala", OpenGL: "opengl", Vulkan: "vulkan",
  GLSL: "opengl", "SPIR-V": "hardware", LLVM: "llvm", MLIR: "llvm",
  PyTorch: "pytorch", ONNX: "onnx", CUDA: "nvidia", React: "react",
  "Vue.js": "vuedotjs", FastAPI: "fastapi", Electron: "electron", MySQL: "mysql", nginx: "nginx",
};
const source = computed(() => icons[`../assets/tech-icons/${slugs[props.name] ?? "code"}.svg`]);
</script>

<template>
  <img class="tech-icon" :src="source" alt="" aria-hidden="true" width="16" height="16" />
</template>

<style scoped>
.tech-icon { display: block; width: 1rem; height: 1rem; flex: 0 0 1rem; object-fit: contain; }
</style>
