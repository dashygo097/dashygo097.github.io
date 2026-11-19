<script setup lang="ts">
import TechGroup from "./TechGroup.vue";
import GitHubStats from "./GitHubStats.vue";

const username = "dashygo097";
const tools = [
  {
    title: "Operating systems",
    items: ["macOS", "Linux", "LineageOS", "Windows"],
  },
  {
    title: "Terminal & version control",
    items: ["WezTerm", "Zsh", "Git", "GitHub"],
  },
  {
    title: "Editors & browsing",
    items: ["Neovim", "Vim", "Visual Studio Code", "Arc", "Google"],
  },
];
const languages = [
  "C",
  "C++",
  "Rust",
  "Python",
  "JavaScript",
  "TypeScript",
  "Scala",
  "HTML",
  "CSS",
  "LaTeX",
];
const interests = [
  { title: "Digital IC", items: ["Verilog", "SystemVerilog", "Chisel"] },
  { title: "Graphics", items: ["OpenGL", "Vulkan", "GLSL", "SPIR-V"] },
  { title: "Compilers", items: ["LLVM", "MLIR"] },
  { title: "Machine Learning & AI Infra", items: ["PyTorch", "ONNX", "CUDA"] },
  {
    title: "Web & App",
    items: ["React", "Vue.js", "FastAPI", "Electron", "MySQL", "nginx"],
  },
];
</script>

<template>
  <a class="skip-link" href="#main">Skip to content</a>
  <div class="page" id="top">
    <header class="site-header">
      <a class="wordmark" href="#top" aria-label="dashygo097 home"
        >{{ username }}<span aria-hidden="true">.</span></a
      >
      <nav aria-label="Main navigation">
        <a href="#toolkit">Toolkit</a>
        <a href="#interests">Interests</a>
        <a :href="`https://github.com/${username}`">GitHub</a>
      </nav>
    </header>

    <main id="main">
      <section class="intro" aria-labelledby="intro-heading">
        <p class="eyebrow">HELLO, WORLD</p>
        <h1 id="intro-heading">
          Hi there, I’m {{ username }}
          <span class="wave" role="img" aria-label="waving hand">👋</span>
        </h1>
        <p class="intro-detail">
          Digital IC · Graphics · Compilers · AI infrastructure · Web & App
        </p>
        <a class="button" :href="`https://github.com/${username}`"
          >Find me on GitHub</a
        >
      </section>

      <section
        id="toolkit"
        class="content-section"
        aria-labelledby="toolkit-heading"
      >
        <div class="section-heading">
          <h2 id="toolkit-heading">Dev tools & setups</h2>
          <p>My everyday environment.</p>
        </div>
        <div class="tools-grid">
          <TechGroup v-for="group in tools" :key="group.title" v-bind="group" />
        </div>
        <div class="languages">
          <TechGroup title="Programming languages" :items="languages" />
        </div>
      </section>

      <section
        id="interests"
        class="content-section"
        aria-labelledby="interests-heading"
      >
        <div class="section-heading">
          <h2 id="interests-heading">Tech stacks & interests</h2>
          <p>Things I like exploring.</p>
        </div>
        <div class="interest-grid">
          <TechGroup
            v-for="group in interests"
            :key="group.title"
            v-bind="group"
          />
        </div>
      </section>

      <section class="content-section" aria-labelledby="stats-heading">
        <div class="section-heading">
          <h2 id="stats-heading">On GitHub</h2>
          <a :href="`https://github.com/${username}?tab=repositories`"
            >Browse repositories</a
          >
        </div>
        <GitHubStats :username="username" />
      </section>
    </main>

    <footer>
      <span>© {{ new Date().getFullYear() }} {{ username }}</span
      ><a href="#top">Back to top</a>
    </footer>
  </div>
</template>

<style scoped>
.page {
  max-width: 62rem;
  padding: 1.5rem 2rem 0;
  margin: auto;
}
.site-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
  padding: 1rem 1.25rem;
  border: 1px solid var(--border);
  border-radius: 1rem;
  background: #1c1e24b3;
  -webkit-backdrop-filter: blur(16px);
  backdrop-filter: blur(16px);
}
.wordmark {
  color: var(--text);
  font-weight: 600;
  letter-spacing: -0.025em;
}
.wordmark span {
  color: var(--accent);
}
nav {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  font-size: 0.875rem;
}
nav a {
  color: var(--text-secondary);
}
.intro {
  padding: 6rem 0 4.5rem;
  max-width: 47rem;
}
.eyebrow {
  margin: 0 0 1.25rem;
  color: var(--text-secondary);
  font-size: 0.8125rem;
  font-family: var(--mono);
  letter-spacing: 0.12em;
}
h1 {
  margin: 0;
  font-size: clamp(2rem, 4.5vw, 2.75rem);
  font-weight: 600;
  line-height: 1.25;
  letter-spacing: -0.04em;
  overflow-wrap: anywhere;
}
.wave {
  display: inline-block;
  font-size: 0.8em;
}
.intro-text {
  max-width: 37rem;
  margin: 1.5rem 0 1rem;
  color: var(--text-secondary);
  font-size: 1.125rem;
  line-height: 1.8;
}
.intro-detail {
  color: var(--text-secondary);
  font-size: 0.875rem;
  line-height: 1.8;
}
.button {
  display: inline-flex;
  align-items: center;
  min-height: 2.75rem;
  margin-top: 1rem;
  padding: 0.65rem 1rem;
  border: 1px solid #ffffff25;
  border-radius: 0.75rem;
  background: linear-gradient(#343943, #292e37);
  color: var(--text);
  font-size: 0.875rem;
  font-weight: 500;
  box-shadow: inset 0 1px 0 #ffffff0c;
}
.button:hover {
  background: #3b424d;
  color: white;
}
.content-section {
  padding: 2.5rem 0 3rem;
  border-top: 1px solid var(--border);
}
.section-heading {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.5rem 1rem;
  margin-bottom: 2rem;
}
h2 {
  margin: 0;
  font-size: 1.375rem;
  letter-spacing: -0.025em;
  font-weight: 600;
}
.section-heading p,
.section-heading a {
  margin: 0;
  color: var(--text-secondary);
  font-size: 0.875rem;
}
.section-heading a {
  text-decoration: underline;
  text-underline-offset: 4px;
}
.tools-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 2rem;
}
.languages {
  margin-top: 2.5rem;
}
.interest-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 2rem 3rem;
}
footer {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
  padding: 1.75rem 0;
  border-top: 1px solid var(--border);
  color: var(--text-secondary);
  font-size: 0.8125rem;
}
@media (max-width: 700px) {
  .page {
    padding: 1rem 1.25rem 0;
  }
  .site-header {
    padding: 0.875rem 1rem;
  }
  nav {
    gap: 1rem;
  }
  .intro {
    padding: 4rem 0 3rem;
  }
  .tools-grid {
    grid-template-columns: 1fr;
  }
  .interest-grid {
    grid-template-columns: 1fr;
  }
  .section-heading {
    margin-bottom: 1.5rem;
  }
  .content-section {
    padding-block: 2rem;
  }
}
</style>
