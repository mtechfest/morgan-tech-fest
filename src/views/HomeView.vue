<script setup>
import TeamworkIcon from '@/components/icons/IconTeamwork.vue'
import ConferenceIcon from '@/components/icons/IconConference.vue'
import PurpleGlitterIcon from '@/components/icons/IconPurpleGlitter.vue'
import YellowGlitterIcon from '@/components/icons/IconYellowGlitter.vue'
import SmallPurpleGlitterIcon from '@/components/icons/IconSmPurpleGlitter.vue'
import SmallYellowGlitterIcon from '@/components/icons/IconSmYellowGlitter.vue'
import ArrowExternalIcon from '@/components/icons/IconArrowExternal.vue'
import MessageIcon from '@/components/icons/IconMessage.vue'
import TwitterIcon from '@/components/icons/IconTwitter.vue'
import InstagramIcon from '@/components/icons/IconInstagram.vue'
import GithubIcon from '@/components/icons/IconGithub.vue'
import DiscordIcon from '@/components/icons/IconDiscord.vue'

import FAQItem from '@/components/FAQItem.vue'

const schedule = [
  'Tech Talk',
  'Workshop',
  'Job Fair',
  'Poster Session',
  'Award',
  'Networking',
  'Panel Session',
  'Project'
]

const panelist = [
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694034987/MorganTechFest/panelist/Dr._Md_Rahman_nzhtz2.png',
    name: 'Mahmudur Rahman'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694035269/MorganTechFest/panelist/Dr._Oludare_Owolabi_asncbj.png',
    name: 'Dr. Oludare Owolabi'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694035437/MorganTechFest/panelist/Prof._Tomasz_Durakiewicz_1_mumive.png',
    name: 'Prof. Tomasz Durakiewicz'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694034703/MorganTechFest/panelist/Monir_Sharker_paihad.png',
    name: 'Monir Sharker'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694034333/MorganTechFest/panelist/taofeek_mzebqx.png',
    name: 'Taofeek Obafemi Babatunde'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694035608/MorganTechFest/panelist/Michael_McDonald_nvrpar.png',
    name: 'Michael Mcdonald'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694035824/MorganTechFest/panelist/Mike_Hoggard_copy_csuu5w.png',
    name: 'Micheal Hoggard'
  },
  {
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1694119054/MorganTechFest/panelist/Rebecca_Rosena_q3vxzt.png',
    name: 'Rebecca Rosena'
  }
]

const partners = [
  {
    name: 'Bloomberg',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912315/MorganTechFest/patners/imgbin-new-york-city-bloomberg-logo-business-public-relations-others-phb3ccrMbmzt3GtmTYPU3gDiM_h0rzlb.png'
  },

  {
    name: 'Goldman Sachs',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912314/MorganTechFest/patners/Gold-1_mtkyt3.png'
  },
  {
    name: 'Roku',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912315/MorganTechFest/patners/roku-logo_xzx5t7.png'
  },
  {
    name: 'Amazon',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912314/MorganTechFest/patners/Amazon-Logo_uwtnvr.png'
  },
  {
    name: 'JS Technology Academy',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912315/MorganTechFest/patners/JOS-Tech-Logo_yyryyj.png'
  },
  {
    name: 'Microsoft',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912314/MorganTechFest/patners/png-transparent-microsoft-logo-microsoft-thumbnail_nltjdz.png'
  },
  {
    name: 'M&T Tech',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912314/MorganTechFest/patners/mtb_yellow_1000x400_bndhia.png'
  },
  {
    name: 'Kiwi bot',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912314/MorganTechFest/patners/kiwibot_owler_20210302_222701_original_gtrqkk.png'
  },
  {
    name: 'HBCU',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912315/MorganTechFest/patners/Copy_of_Adobe_HBCU_20x20_HBCU_Fellowship_3_ss0cdo.png'
  },
  {
    name: 'Fannie Mae',
    img: 'https://res.cloudinary.com/ojay-dev/image/upload/v1693912315/MorganTechFest/patners/FNMAL_BIG-c2a1e64d_tlda8h.png'
  }
]

const FaqQuestionsAnswers = [
  {
    question: 'What exactly is Morgan TechFest?',
    answer: `Morgan TechFest is a two-day in-person student-led tech conference that brings together developers, researchers, and tech enthusiasts across universities in the US.`
  },
  {
    question: 'Who is eligible to participate in Morgan TechFest?',
    answer: `University students (undergraduate, graduate, or postgraduate)`
  },
  {
    question: 'Which specific domain of research does Morgan TechFest emphasize?',
    answer: `All tech-related research (AI, VR, blockchain, software, etc.)`
  },
  {
    question: 'Are there any accolades presented for exceptional research contributions?',
    answer: `Yes. We award the best 3 research papers.`
  },
  {
    question: 'Is Morgan TechFest accessible to all university students?',
    answer: `Yes! We invite all students to join us at the National Treasure, Morgan State University`
  },
  {
    question: 'How do I go about registering for Morgan TechFest?',
    answer: `Just click on the registration button on this page and fill out the form.`
  },
  {
    question: 'What steps can I take to engage my university in Morgan TechFest?',
    answer: `Connect us with your university or department, and we will take it from there.`
  },
  {
    question: 'What if I am doing nothing related to technology? Can I come?',
    answer: `Yes! Morgan TechFest is open to anyone interested in developing a career or business in the tech space. We have put together robust educational programs to help anyone interested in starting a career or business in the field.`
  },
  {
    question: 'Morgan TechFest is when?',
    answer: `It is a two-day event, starting on Thursday, November 9, from 10 a.m. to 4 p.m. and Friday, November 10, from 10 a.m. to 4 p.m. `
  },
  {
    question: 'Are provisions like breakfast, lunch, and dinner included?',
    answer: `Yes! Food and drinks are available, and we also do our best to accommodate all kinds of dietary`
  },
  {
    question: 'How do I get there?',
    answer: `We provide transportation support through your university, department, and student organization.`
  },
  {
    question: 'Is Morgan TechFest free?',
    answer: `Yes. It's free and made for all students.`
  },
  {
    question: 'Is Morgan TechFest in-person?',
    answer: `Yes! It is an in-person event.`
  },
  {
    question: 'Location?',
    answer: `University Student Center, Calvin and Tina Tyler Ballroom, Morgan State University.`
  },
  {
    question: 'Is it specific to any department?',
    answer: `No. In fact, we want to expose you to how technology is altering your field and how you can switch or channel your career towards it.`
  },
  {
    question: 'Any other opportunities?',
    answer: `Yes! So much more! You’ve got to network with tech professionals, apply for jobs, get awarded for your innovative tech-driven research, and network with other students, developers, and researchers.`
  }
]
</script>

<template>
  <div id="hero">
    <div class="hidden bg-blue-theme pt-14 lg:block lg:pb-[100px]">
      <div class="mx-auto lg:max-w-5xl">
        <div class="hero-grid">
          <span class="hero-text">Discover</span>
          <div class="mx-auto"><PurpleGlitterIcon /></div>
          <div><TeamworkIcon /></div>
        </div>

        <div class="hero-grid">
          <div><ConferenceIcon /></div>
          <div class="mx-auto"><YellowGlitterIcon /></div>
          <span class="hero-text">Network</span>
        </div>

        <div class="hero-grid">
          <span class="hero-text">Innovate</span>
          <div class="mx-auto"><PurpleGlitterIcon /></div>

          <div class="flex gap-x-10">
            <div class="max-w-[163px]">
              <span class="font-urbanist text-base font-black uppercase text-[#F68F21]">Date:</span>
              <p class="font-urbanist text-[22px] text-white">Thurs Nov 16, Fri Nov 17, 2023</p>
            </div>
            <div class="max-w-[163px]">
              <span class="font-urbanist text-base font-black uppercase text-[#F68F21]"
                >Venue:</span
              >
              <p class="font-urbanist text-[22px] text-white">Calvin & Tina Tyler Ballroom</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="block bg-blue-theme pb-[100px] pt-8 lg:hidden">
      <div class="px-6 lg:px-0">
        <div class="hero-grid">
          <span class="hero-text">Discover</span>

          <div class="mx-auto"><SmallPurpleGlitterIcon /></div>

          <span class="hero-text">Network</span>

          <div class="mx-auto"><SmallYellowGlitterIcon /></div>

          <span class="hero-text">Innovate</span>

          <div class="mx-auto"><SmallPurpleGlitterIcon /></div>

          <div class="flex gap-x-10">
            <div class="max-w-[163px]">
              <span class="font-urbanist text-base font-black uppercase text-[#F68F21]">Date:</span>
              <p class="font-urbanist text-[22px] text-white">Thurs Nov 16, Fri Nov 17, 2023</p>
            </div>
            <div class="max-w-[163px]">
              <span class="font-urbanist text-base font-black uppercase text-[#F68F21]">Date:</span>
              <p class="font-urbanist text-[22px] text-white">Thurs Nov 16, Fri Nov 17, 2023</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="video-section">
    <div class="lg:mx-auto lg:max-w-4xl">
      <div class="video-container">
        <iframe
          src="https://www.youtube.com/embed/rI_NHdC4kEY"
          title="Networking Session"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </div>

  <div class="bg-[#FEF8F0] px-6 pb-[109px] pt-4 md:pb-[174px]" id="about">
    <div class="lg:mx-auto lg:max-w-4xl">
      <div class="flex flex-col items-center gap-x-9 gap-y-4 md:flex-row">
        <h2 class="sub-title-dark w-full">About Us</h2>
        <p class="max-w-[626px] font-urbanist text-xl font-normal">
          Morgan TechFest is A student-led tech conference sponsored through the computer science
          department at Morgan State University.
        </p>
      </div>
    </div>

    <div class="mt-11 lg:mx-auto lg:max-w-5xl">
      <div class="flex flex-col items-center gap-x-12 gap-y-12 md:flex-row">
        <p class="font-urbanist text-xl font-normal md:w-1/2">
          Morgan TechFest focuses on educating students about the influence of technology on their
          career paths, facilitating networking with tech experts, enabling job opportunities in the
          tech industry, and recognizing outstanding tech-innovative research through poster
          showcases and awards.
        </p>

        <div class="md:w-1/2">
          <img
            src="https://res.cloudinary.com/ojay-dev/image/upload/v1693949804/MorganTechFest/gallery/DYO_0087_websize_1_svatmt.png"
            alt="conference"
            class="w-full"
          />
        </div>
      </div>
    </div>
  </div>

  <div class="bg-blue-theme px-6 pb-[71px] pt-[51px] lg:pb-[239px] lg:pt-[112px]" id="schedule">
    <div class="lg:mx-auto lg:max-w-5xl">
      <h2 class="sub-title mx-auto">schedule</h2>

      <div class="mt-9 grid grid-cols-2 gap-x-6 gap-y-8 sm:grid-cols-3 md:mt-12 lg:grid-cols-4">
        <template v-for="item in schedule" :key="item">
          <span class="schedule-pill">{{ item }}</span>
        </template>
      </div>

      <div class="mt-14 flex justify-center lg:mt-16">
        <RouterLink
          to="/"
          class="flex items-center gap-x-4 rounded-[44px] border-2 border-white px-6 py-4 font-urbanist text-lg font-semibold text-white hover:text-white md:text-2xl lg:border-0 lg:py-6 lg:text-3xl"
          >Check full schedule here
          <ArrowExternalIcon />
        </RouterLink>
      </div>

      <div class="mt-24 lg:mt-40" id="speakers">
        <h2 class="sub-title mx-auto">speakers</h2>

        <div
          class="mt-6 flex flex-col items-center justify-center gap-x-8 gap-y-6 lg:mt-24 lg:flex-row"
        >
          <div class="speaker-img-container">
            <img
              src="https://res.cloudinary.com/ojay-dev/image/upload/v1694032219/MorganTechFest/speakers/1692902593759_1_thgonx.jpg"
              alt="Dr. Yacob Astatke"
              class="object-cover"
            />

            <span class="speaker-name">Dr. Yacob Astatke</span>
          </div>

          <div class="speaker-img-container">
            <img
              src="https://res.cloudinary.com/ojay-dev/image/upload/v1694030711/MorganTechFest/speakers/Akers_Tim_r9h7yl.jpg"
              alt="Dr. Timothy A. Akers"
              class="w-full object-cover"
            />

            <span class="speaker-name">Dr. Timothy A. Akers</span>
          </div>

          <div class="speaker-img-container">
            <img
              src="https://res.cloudinary.com/ojay-dev/image/upload/v1694032777/MorganTechFest/speakers/hongtao-yu_xumojr.jpg"
              alt="Dr. Hongtao Yu"
              class="object-cover"
            />

            <span class="speaker-name">Dr. Hongtao Yu</span>
          </div>
        </div>
      </div>

      <div class="mt-24 lg:mt-40">
        <h2 class="sub-title mx-auto">Panelist</h2>

        <div class="panelist-section">
          <template v-for="item in panelist" :key="item.name">
            <img :src="item.img" :alt="item.name" class="panelist-img"
          /></template>
        </div>
      </div>
    </div>
  </div>

  <div class="px-6 pb-16 pt-14 lg:mx-auto lg:max-w-5xl lg:pb-52 lg:pt-40" id="sponsors">
    <h2 class="sub-title-dark mx-auto">sponsors</h2>

    <div class="mt-20 flex flex-col items-center gap-y-16 lg:gap-y-24">
      <div>
        <img
          src="https://res.cloudinary.com/ojay-dev/image/upload/v1693912316/MorganTechFest/sponsors/gold_sponsor_efuamu.svg"
          alt="Bloomberg"
        />
      </div>

      <div>
        <img
          src="https://res.cloudinary.com/ojay-dev/image/upload/v1693912315/MorganTechFest/sponsors/silver_sponsor_nytcof.svg"
          alt="HBCU"
        />
      </div>
    </div>

    <div
      class="mt-11 rounded-[27px] bg-[#313036] px-4 pb-10 pt-12 lg:mt-32 lg:rounded-[36px] lg:pl-24 lg:pr-16"
    >
      <p class="font-urbanist text-base font-normal text-white lg:text-xl">
        Morgan TechFest provides an outstanding platform for you to draw in accomplished students,
        developers, and researchers, elevate brand visibility, and explore pioneering technological
        research. We present a diverse array of methods to support you in refining your engagement
        and realizing your goals.
      </p>

      <p class="mt-9 font-urbanist text-base font-bold text-white lg:mt-[60px] lg:text-xl">
        Learn more about the opportunity to become a Gold sponsor or explore other available
        sponsorship tiers for the upcoming event. Please send an email to:
        <a href="mailto:morgantechfest@gmail.com" target="_blank" rel="noopener noreferrer"
          >morgantechfest@gmail.com</a
        >
      </p>

      <div class="mt-14 flex justify-center lg:mt-16">
        <RouterLink
          to="/"
          class="flex items-center gap-x-4 rounded-[44px] border-2 border-white px-6 py-4 font-urbanist text-lg font-semibold text-white hover:text-white md:text-2xl lg:border-0 lg:py-6 lg:text-3xl"
          >Become a Sponsor
          <ArrowExternalIcon />
        </RouterLink>
      </div>
    </div>

    <div class="mt-[84px] lg:mt-[158px]">
      <h2 class="sub-title-dark mx-auto">partners</h2>

      <div
        class="mt-5 grid grid-cols-2 items-center justify-center gap-x-9 gap-y-10 md:flex md:flex-wrap lg:mt-[78px] lg:gap-x-[128px] lg:gap-y-16"
      >
        <template v-for="item in partners" :key="item.name">
          <div class="w-fit">
            <img :src="item.img" :alt="item.name" />
          </div>
        </template>
      </div>
    </div>
  </div>

  <div class="bg-blue-theme px-6 pb-20 pt-[86px] lg:pb-11 lg:pt-32">
    <div class="lg:mx-auto lg:max-w-5xl">
      <h2 class="sub-title mx-auto">gallery</h2>

      <div class="mt-7">
        <div class="hidden gap-x-4 overflow-auto md:flex lg:gap-x-7">
          <div>
            <img
              src="https://res.cloudinary.com/ojay-dev/image/upload/v1693949821/MorganTechFest/gallery/_PAG0547_1_1_z7ffvg.png"
              alt="gallery"
            />
          </div>

          <div>
            <img
              src="https://res.cloudinary.com/ojay-dev/image/upload/v1693912317/MorganTechFest/gallery/_PAG05472_b2x7ra.png"
              alt="gallery"
            />
          </div>
        </div>

        <div class="flex gap-x-4 overflow-auto md:hidden lg:gap-x-7">
          <img
            src="https://res.cloudinary.com/ojay-dev/image/upload/v1693949821/MorganTechFest/gallery/_PAG0547_1_1_z7ffvg.png"
            alt="gallery"
          />

          <img
            src="https://res.cloudinary.com/ojay-dev/image/upload/v1693912317/MorganTechFest/gallery/_PAG05472_b2x7ra.png"
            alt="gallery"
          />
        </div>

        <div class="mt-14 flex justify-center lg:mt-16">
          <a
            href="https://drive.google.com/drive/folders/15Vswx6fn4A6U_I6ScyX54fm6tYN70gGC?usp=sharing"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-x-4 rounded-[44px] border-2 border-white px-6 py-4 font-urbanist text-lg font-semibold text-white hover:text-white md:text-2xl lg:border-0 lg:py-6 lg:text-3xl"
            >View album
            <ArrowExternalIcon />
          </a>
        </div>
      </div>
    </div>

    <div class="mt-16 lg:mx-auto lg:mt-44 lg:max-w-5xl" id="faq">
      <h2 class="sub-title mx-auto">FAQ</h2>

      <div class="mt-5 lg:mt-6" v-for="item in FaqQuestionsAnswers" :key="item.name">
        <FAQItem :question="item.question" :answer="item.answer" />
      </div>
    </div>

    <div class="mt-[84px] flex justify-center gap-x-3">
      <a
        href="mailto:morgantechfest@gmail.com"
        target="_blank"
        rel="noopener noreferrer"
        class="block border border-[#D6D6D6] px-2 py-[14px]"
        ><MessageIcon
      /></a>

      <a
        href="https://twitter.com/MorganTechFest"
        target="_blank"
        rel="noopener noreferrer"
        class="block border border-[#D6D6D6] px-2 py-[14px]"
        ><TwitterIcon
      /></a>

      <a
        href=" https://www.instagram.com/morgantechfest/ "
        target="_blank"
        rel="noopener noreferrer"
        class="block border border-[#D6D6D6] px-2 py-[14px]"
        ><InstagramIcon
      /></a>

      <a
        href="https://github.com/morgantechfest"
        target="_blank"
        rel="noopener noreferrer"
        class="block border border-[#D6D6D6] px-2 py-[14px]"
        ><GithubIcon
      /></a>

      <a
        href="https://www.discord.com/channels/morgantechfest"
        target="_blank"
        rel="noopener noreferrer"
        class="block border border-[#D6D6D6] px-2 py-[14px]"
        ><DiscordIcon
      /></a>
    </div>
  </div>
</template>

<style scoped>
.hero-grid {
  @apply relative grid items-center justify-center gap-y-4 lg:grid-cols-[384px_0.4fr_384px] lg:gap-y-0;
}

.hero-text {
  @apply block max-w-[376px] text-center font-bebas text-8xl font-normal text-white lg:text-left lg:text-[112px];
}

.sub-title {
  @apply block max-w-[376px] text-center font-bebas text-8xl font-normal text-white lg:text-[112px];
}
.sub-title-dark {
  @apply block max-w-[376px] text-center font-bebas text-8xl font-normal text-[#121139]  lg:text-[112px];
}

.video-section {
  @apply relative px-6 pb-8 lg:px-0  lg:pb-[100px] lg:pt-20;
  background: linear-gradient(to bottom, #000080 0%, #000080 40%, #fef8f0 40%, #fef8f0 100%);
}

.video-container {
  @apply relative  h-0 w-full pb-[56.25%];
}

.video-container iframe {
  @apply absolute left-0 top-0 h-full w-full rounded-[30px];
}

.schedule-pill {
  @apply flex h-20 items-center justify-center rounded-[73px] px-6 text-center font-urbanist text-lg font-bold text-white lg:h-24 lg:text-2xl;
  border: 3px solid rgba(255, 255, 255, 0.2);
  background: linear-gradient(
      136deg,
      rgba(177, 177, 177, 0.32) 5.24%,
      rgba(54, 53, 103, 0.2) 51.01%
    ),
    rgba(49, 48, 54, 0.3);
  backdrop-filter: blur(3.297909736633301px);
}

.speaker-img-container {
  @apply relative h-[375px] w-[328px] overflow-hidden rounded-3xl;
}

.speaker-img-container::before {
  @apply absolute left-0 top-0 h-full w-full rounded-3xl;
  content: '';
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.8) 9.19%, rgba(0, 0, 0, 0) 34.63%);
}

.speaker-name {
  @apply absolute bottom-6 left-10 z-10 font-bebas text-2xl font-normal text-white;
}

.panelist-section {
  @apply mt-6 flex gap-x-5 gap-y-9 overflow-x-auto md:grid md:grid-cols-4 lg:mt-24;
}

.panelist-img {
  @apply relative block h-[300px] w-[263px] rounded-2xl object-cover object-center;
}

.panelist-img-container {
  @apply relative h-full w-full;
}

.panelist-img-container::before {
  @apply absolute left-0 top-0 h-full w-full rounded-3xl;
  content: '';
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.8) 9.19%, rgba(0, 0, 0, 0) 34.63%);
}

.panelist-name {
  @apply absolute bottom-6 left-10 z-10 font-bebas text-2xl font-normal text-white;
}
</style>
