<script setup>
import { computed } from 'vue';
import projectsData from './data/projects.json';

// MAPA DE COLORES
const getTechColor = (tech) => {
  const map = {
    'Apache': 'text-red-300 bg-red-900/20 border-red-800/50',
    'Git': 'text-orange-400 bg-orange-900/20 border-orange-800/50',
    'Docker': 'text-blue-400 bg-blue-900/20 border-blue-800/50',
    'PostgreSQL': 'text-indigo-300 bg-indigo-900/20 border-indigo-800/50',
    'MySQL': 'text-blue-300 bg-blue-900/20 border-blue-800/50',
    'PHP': 'text-violet-400 bg-violet-900/20 border-violet-800/50',
    'Phalcon': 'text-teal-300 bg-teal-900/20 border-teal-800/50',
    'Phalcon API': 'text-teal-300 bg-teal-900/20 border-teal-800/50',
    'Laravel': 'text-red-500 bg-red-900/20 border-red-800/50',
    'JavaScript': 'text-yellow-300 bg-yellow-900/20 border-yellow-800/50',
    'Vue.js': 'text-emerald-400 bg-emerald-900/20 border-emerald-800/50',
    'React': 'text-cyan-400 bg-cyan-900/20 border-cyan-800/50',
    'HTML': 'text-orange-500 bg-orange-900/20 border-orange-800/50',
    'CSS': 'text-sky-400 bg-sky-900/20 border-sky-800/50',
    'Bootstrap': 'text-purple-400 bg-purple-900/20 border-purple-800/50',
    'jQuery': 'text-blue-200 bg-blue-900/20 border-blue-800/50',
    'Google Maps API': 'text-green-300 bg-green-900/20 border-green-800/50',
    'PayPal API': 'text-blue-400 bg-blue-900/20 border-blue-800/50',
    'Vite': 'text-purple-300 bg-purple-900/20 border-purple-800/50',
    'Python': 'text-yellow-400 bg-yellow-900/20 border-yellow-800/50', // Agregado por si decides poner el de placas
    'OpenCV': 'text-green-400 bg-green-900/20 border-green-800/50',   // Agregado por si decides poner el de placas
  };
  return map[tech] || 'text-slate-300 bg-slate-700/50 border-slate-600';
};

// SIN ORDENAMIENTO AUTOMÁTICO - Respetamos tu orden del JSON
const atyProjects = computed(() => projectsData.filter(p => p.grupo === 'aty'));
const freelanceProjects = computed(() => projectsData.filter(p => p.grupo === 'freelance'));
</script>

<template>
  <div class="min-h-screen bg-dark-bg font-sans selection:bg-primary selection:text-black relative overflow-hidden flex flex-col">
    
    <div class="fixed top-0 left-0 w-full h-full pointer-events-none z-0">
      <div class="absolute top-[-10%] left-[-10%] w-[600px] h-[600px] bg-primary/5 rounded-full blur-[120px]"></div>
      <div class="absolute bottom-[-10%] right-[-10%] w-[600px] h-[600px] bg-purple-500/5 rounded-full blur-[120px]"></div>
    </div>

    <header class="relative max-w-6xl mx-auto px-6 py-20 md:py-28 text-center z-10">
      <div class="inline-block px-3 py-1 mb-6 text-xs font-mono text-primary bg-primary/10 rounded-full border border-primary/20 animate-pulse">
        Disponible para Proyectos Inmediatos
      </div>
      
      <h1 class="text-5xl md:text-7xl font-extrabold text-white tracking-tight mb-6">
        Gaspar <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-purple-400">Cardos</span>
      </h1>
      
      <p class="text-xl text-slate-400 max-w-2xl mx-auto mb-8 leading-relaxed">
        <strong class="text-white">Desarrollador Web Full Stack</strong>.
        <br class="hidden md:block"/>
        Transformo lógica de negocio compleja en sistemas web robustos y escalables.
      </p>

      <div class="flex justify-center mb-10">
        <a href="#contacto" class="px-8 py-4 bg-primary text-dark-bg font-bold rounded-lg hover:bg-white transition-all transform hover:scale-105 shadow-lg shadow-primary/20 text-lg">
          Contáctame Ahora
        </a>
      </div>
      
      <div class="flex flex-wrap justify-center gap-6 md:gap-12 text-slate-500 text-sm font-mono border-t border-slate-800/50 pt-8 max-w-3xl mx-auto">
        <div class="flex items-center gap-2">
          <div class="w-2 h-2 rounded-full bg-primary"></div>
          <span class="text-white font-bold">5+</span> Años Exp.
        </div>
        <div class="flex items-center gap-2">
          <div class="w-2 h-2 rounded-full bg-purple-500"></div>
          <span class="text-white font-bold">15+</span> Proyectos
        </div>
        <div class="flex items-center gap-2">
          <div class="w-2 h-2 rounded-full bg-green-500"></div>
          <span class="text-white font-bold">Full Stack</span> (Backend Heavy)
        </div>
      </div>
    </header>

    <main class="relative max-w-7xl mx-auto px-6 pb-24 z-10 flex-grow">
      
      <section class="mb-32">
        <div class="flex items-end gap-4 mb-10">
          <h2 class="text-3xl md:text-4xl font-bold text-white">Experiencia Institucional</h2>
          <div class="h-px bg-slate-800 flex-grow mb-2"></div>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 auto-rows-fr">
          <div 
            v-for="project in atyProjects" 
            :key="project.id"
            class="group relative bg-card-bg rounded-xl border border-slate-800 hover:border-slate-600 transition-all duration-300 hover:shadow-2xl hover:shadow-primary/5 overflow-hidden flex flex-col"
          >
            <div class="flex items-center gap-2 px-4 py-3 border-b border-slate-800/50 bg-slate-900/50">
              <div class="flex gap-1.5">
                <div class="w-2.5 h-2.5 rounded-full bg-red-500/20 group-hover:bg-red-500 transition-colors"></div>
                <div class="w-2.5 h-2.5 rounded-full bg-yellow-500/20 group-hover:bg-yellow-500 transition-colors"></div>
                <div class="w-2.5 h-2.5 rounded-full bg-green-500/20 group-hover:bg-green-500 transition-colors"></div>
              </div>
              <div class="ml-auto text-[10px] font-mono text-slate-500 uppercase tracking-wider">
                {{ project.cliente }}
              </div>
            </div>

            <div class="p-6 flex flex-col flex-grow">
              <div class="flex justify-between items-start mb-4">
                <h3 class="text-xl font-bold text-slate-100 group-hover:text-primary transition-colors leading-tight">
                  {{ project.titulo }}
                </h3>
                <span class="text-xs font-mono text-slate-500 bg-slate-900 px-2 py-1 rounded border border-slate-800 whitespace-nowrap ml-2">
                  {{ project.periodo }}
                </span>
              </div>
              <p class="text-slate-400 text-sm leading-relaxed mb-6 flex-grow">
                {{ project.descripcion }}
              </p>
              <div class="flex flex-wrap gap-2 mt-auto">
                <span v-for="(tech, index) in project.stack" :key="index" :class="['text-[10px] font-mono px-2 py-1 rounded border transition-colors', getTechColor(tech)]">
                  {{ tech }}
                </span>
              </div>
            </div>

            <a v-if="project.link" :href="project.link" target="_blank" class="absolute top-4 right-4 p-2 bg-slate-800 text-primary rounded-lg border border-slate-700 opacity-0 group-hover:opacity-100 transition-opacity hover:bg-slate-700 z-20 cursor-pointer">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
              </svg>
            </a>

          </div>
        </div>
      </section>

      <section>
        <div class="flex items-end gap-4 mb-10">
          <h2 class="text-3xl md:text-4xl font-bold text-white">Freelance & Consultoría</h2>
          <div class="h-px bg-slate-800 flex-grow mb-2"></div>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 auto-rows-fr">
          <div 
            v-for="project in freelanceProjects" 
            :key="project.id"
            class="group relative bg-card-bg rounded-xl border border-slate-800 hover:border-slate-600 transition-all duration-300 hover:shadow-2xl hover:shadow-primary/5 overflow-hidden flex flex-col"
          >
            <div class="flex items-center gap-2 px-4 py-3 border-b border-slate-800/50 bg-slate-900/50">
              <div class="flex gap-1.5">
                <div class="w-2.5 h-2.5 rounded-full bg-red-500/20 group-hover:bg-red-500 transition-colors"></div>
                <div class="w-2.5 h-2.5 rounded-full bg-yellow-500/20 group-hover:bg-yellow-500 transition-colors"></div>
                <div class="w-2.5 h-2.5 rounded-full bg-green-500/20 group-hover:bg-green-500 transition-colors"></div>
              </div>
              <div class="ml-auto text-[10px] font-mono text-slate-500 uppercase tracking-wider">
                {{ project.cliente }}
              </div>
            </div>

            <div class="p-6 flex flex-col flex-grow">
              <div class="flex justify-between items-start mb-4">
                <h3 class="text-xl font-bold text-slate-100 group-hover:text-primary transition-colors leading-tight">
                  {{ project.titulo }}
                </h3>
                <span class="text-xs font-mono text-slate-500 bg-slate-900 px-2 py-1 rounded border border-slate-800 whitespace-nowrap ml-2">
                  {{ project.periodo }}
                </span>
              </div>
              <p class="text-slate-400 text-sm leading-relaxed mb-6 flex-grow">
                {{ project.descripcion }}
              </p>
              <div class="flex flex-wrap gap-2 mt-auto">
                <span v-for="(tech, index) in project.stack" :key="index" :class="['text-[10px] font-mono px-2 py-1 rounded border transition-colors', getTechColor(tech)]">
                  {{ tech }}
                </span>
              </div>
            </div>
            
            <a v-if="project.link" :href="project.link" target="_blank" class="absolute top-4 right-4 p-2 bg-slate-800 text-primary rounded-lg border border-slate-700 opacity-0 group-hover:opacity-100 transition-opacity hover:bg-slate-700 z-20 cursor-pointer">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
              </svg>
            </a>
          </div>
        </div>
      </section>

    </main>

    <footer id="contacto" class="border-t border-slate-800 bg-slate-900/50 relative z-10 mt-12">
      <div class="max-w-6xl mx-auto px-6 py-16 text-center">
        <h2 class="text-3xl font-bold text-white mb-6">¿Trabajamos juntos?</h2>
        <p class="text-slate-400 mb-10 max-w-xl mx-auto">
          Estoy disponible para unirme a tu equipo y aportar valor inmediato con mi experiencia Full Stack.
        </p>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-12 max-w-4xl mx-auto">
          
          <a href="mailto:gasparcardos@gmail.com" class="flex items-center gap-4 bg-card-bg border border-slate-700 p-4 rounded-xl hover:border-primary transition-colors text-left group hover:bg-slate-800">
            <div class="bg-slate-800 p-3 rounded-lg text-primary group-hover:bg-primary group-hover:text-black transition-colors shrink-0">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
            </div>
            <div class="min-w-0">
              <p class="text-xs text-slate-500 font-mono uppercase mb-0.5">Correo</p>
              <p class="text-white font-medium text-sm truncate">gasparcardos@gmail.com</p>
            </div>
          </a>

          <a href="tel:+529992497115" class="flex items-center gap-4 bg-card-bg border border-slate-700 p-4 rounded-xl hover:border-blue-400 transition-colors text-left group hover:bg-slate-800">
            <div class="bg-slate-800 p-3 rounded-lg text-blue-400 group-hover:bg-blue-400 group-hover:text-black transition-colors shrink-0">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
              </svg>
            </div>
            <div class="min-w-0">
              <p class="text-xs text-slate-500 font-mono uppercase mb-0.5">Llamada</p>
              <p class="text-white font-medium text-sm truncate">+52 999 249 7115</p>
            </div>
          </a>

          <a href="https://wa.me/529992497115" target="_blank" class="flex items-center gap-4 bg-card-bg border border-slate-700 p-4 rounded-xl hover:border-green-500 transition-colors text-left group hover:bg-slate-800">
            <div class="bg-slate-800 p-3 rounded-lg text-green-500 group-hover:bg-green-500 group-hover:text-black transition-colors shrink-0">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/>
              </svg>
            </div>
            <div class="min-w-0">
              <p class="text-xs text-slate-500 font-mono uppercase mb-0.5">WhatsApp</p>
              <p class="text-white font-medium text-sm truncate">Enviar Mensaje</p>
            </div>
          </a>

        </div>
        
        <p class="text-slate-600 text-sm">
          Mérida, Yucatán, México • &copy; {{ new Date().getFullYear() }} Gaspar Cardos.
        </p>
      </div>
    </footer>
  </div>
</template>