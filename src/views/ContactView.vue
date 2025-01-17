<script>
export default {
  data() {
    return {
      tech: [
        {
          id: 1,
          name: 'LinkedIN',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/174/174857.png',
          status: 'work',
          url: 'https://www.linkedin.com/in/febryan-riyadi-2705n412'
        },
        {
          id: 2,
          name: 'GitHub',
          imageUrl: 'https://img.icons8.com/m_sharp/200/FFFFFF/github.png',
          status: 'project list',
          url: 'https://github.com/Brazer27'
        },
        {
          id: 3,
          name: 'E-mail',
          imageUrl: 'https://mailmeteor.com/logos/assets/PNG/Gmail_Logo_512px.png',
          status: 'contact me',
          url: 'mailto:febryanriyadi03@gmail.com'
        },
        {
          id: 4,
          name: 'Instagram',
          imageUrl: 'https://cdn-icons-png.freepik.com/256/15789/15789364.png?semt=ais_hybrid',
          status: 'social media',
          url: 'https://www.instagram.com/febryan_4123?utm_source=ig_web_button_share_sheet&igsh=ZDNlZDc0MzIxNw=='
        }
      ],
    };
  },
  methods: {
    openLink(url) {
      window.open(url, '_blank');
    }
  }
}
</script>


<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-teal-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>My Contacts</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-teal-300">
            Feel free to contact me using the information below.
          </h4>
        </div>
      </header>
      <section>
        <div class="grid grid-cols-2 gap-3 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12 fade-zoom-in">
          <!-- Loop through the tech array -->
          <div v-for="item in tech" :key="item.id">
            <!-- Added @click event to handle link opening -->
            <div @click="openLink(item.url)" class="item-tech flex cursor-pointer items-center gap-2 rounded border border-teal-200 px-2 py-2 hover:bg-teal-200 hover:bg-opacity-10 md:gap-3 lg:px-3">
              <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                <img :src="item.imageUrl" alt="Contact Logo" loading="lazy" class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]" />
              </div>
              <div class="flex items-center text-sm md:text-base lg:text-lg">
                <div class="tech font-medium text-secondary transition-all duration-300 translate-y-0">{{ item.name }}</div>
                <div class="status-tech opacity-0 absolute mt-5 text-[10px] text-teal-200 transition-all duration-300 md:text-xs lg:text-sm">
                  {{ item.status }}
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="text-2xl text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h6>My Phone Number</h6>
          <h7 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-teal-300">
            +62 822 1543 6168
          </h7>
        </div>
      </section>
    </article>
  </div>
</template>


<style scoped>
/* Add custom styles */
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}

svg:hover {
  stroke: #70ffc8;
}

@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.fade-zoom-in {
  animation: fadeZoomIn 2s ease-in-out;
}
</style>
