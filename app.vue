<template>
  <div>
    <div class="shadow-sm p-4">
      <nav class="max-w-7xl mx-auto">
        <h1 class="text-xl font-bold">Andrew Lucas</h1>
      </nav>
    </div>
    <main
      class="max-w-7xl mx-auto mt-4 p-4  flex flex-col gap-8 justify-center items-center md:flex-row-reverse md:items-start ">
      <aside class="md:pl-8 md:border-l">
        <h2 class="text-2xl font-bold">About Me</h2>
        <img :src="profile" alt="Andrew Lucas" class="rounded-full w-32 h-32 mx-auto" />
        <pre class="whitespace-pre-wrap max-w-prose">bio: {{ about }},</pre>
        <div class="font-mono whitespace-pre-wrap max-w-prose mt-2">tech: ["HTML", "CSS", "JavaScript", "Vue.js",
          "React", "Node.js", "Python"],
        </div>
        <div class="font-mono whitespace-pre-wrap max-w-prose mt-2">contact: "{{ email }}",
        </div>
        <div class="flex gap-3 flex-wrap items-center font-mono mt-2">
          socials: [
          <a class="flex gap-0.5 hover:opacity-70" target="_blank" rel="noopener noreferrer" :href="socials.github"><svg
              xmlns="http://www.w3.org/2000/svg" class="size-5" viewBox="0 0 24 24">
              <path fill="currentColor"
                d="M12 .297c-6.63 0-12 5.373-12 12c0 5.303 3.438 9.8 8.205 11.385c.6.113.82-.258.82-.577c0-.285-.01-1.04-.015-2.04c-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729c1.205.084 1.838 1.236 1.838 1.236c1.07 1.835 2.809 1.305 3.495.998c.108-.776.417-1.305.76-1.605c-2.665-.3-5.466-1.332-5.466-5.93c0-1.31.465-2.38 1.235-3.22c-.135-.303-.54-1.523.105-3.176c0 0 1.005-.322 3.3 1.23c.96-.267 1.98-.399 3-.405c1.02.006 2.04.138 3 .405c2.28-1.552 3.285-1.23 3.285-1.23c.645 1.653.24 2.873.12 3.176c.765.84 1.23 1.91 1.23 3.22c0 4.61-2.805 5.625-5.475 5.92c.42.36.81 1.096.81 2.22c0 1.606-.015 2.896-.015 3.286c0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12" />
            </svg>,</a>
          <a class="flex gap-0.5 hover:opacity-70" target="_blank" rel="noopener noreferrer" :href="socials.twitter">
            <svg xmlns="http://www.w3.org/2000/svg" class="size-5" viewBox="0 0 24 24">
              <path fill="currentColor"
                d="M18.901 1.153h3.68l-8.04 9.19L24 22.846h-7.406l-5.8-7.584l-6.638 7.584H.474l8.6-9.83L0 1.154h7.594l5.243 6.932ZM17.61 20.644h2.039L6.486 3.24H4.298Z" />
            </svg>
            ,</a>
          <a class="flex gap-0.5 hover:opacity-70" target="_blank" rel="noopener noreferrer" :href="socials.linkedin">
            <svg xmlns="http://www.w3.org/2000/svg" class="size-5" viewBox="0 0 24 24">
              <path fill="currentColor"
                d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037c-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85c3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065a2.064 2.064 0 1 1 2.063 2.065m1.782 13.019H3.555V9h3.564zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0z" />
            </svg>
            ,</a>
          <a class="flex gap-0.5 hover:opacity-70" target="_blank" rel="noopener noreferrer"
            :href="socials.instagram"><svg xmlns="http://www.w3.org/2000/svg" class="size-5" viewBox="0 0 24 24">
              <path fill="currentColor"
                d="M7.03.084c-1.277.06-2.149.264-2.91.563a5.874 5.874 0 0 0-2.124 1.388a5.878 5.878 0 0 0-1.38 2.127C.321 4.926.12 5.8.064 7.076C.008 8.354-.005 8.764.001 12.023c.007 3.259.021 3.667.083 4.947c.061 1.277.264 2.149.563 2.911c.308.789.72 1.457 1.388 2.123a5.872 5.872 0 0 0 2.129 1.38c.763.295 1.636.496 2.913.552c1.278.056 1.689.069 4.947.063c3.257-.007 3.668-.021 4.947-.082c1.28-.06 2.147-.265 2.91-.563a5.881 5.881 0 0 0 2.123-1.388a5.881 5.881 0 0 0 1.38-2.129c.295-.763.496-1.636.551-2.912c.056-1.28.07-1.69.063-4.948c-.006-3.258-.02-3.667-.081-4.947c-.06-1.28-.264-2.148-.564-2.911a5.892 5.892 0 0 0-1.387-2.123a5.857 5.857 0 0 0-2.128-1.38c-.764-.294-1.636-.496-2.914-.55C15.647.009 15.236-.006 11.977 0C8.718.008 8.31.021 7.03.084m.14 21.693c-1.17-.05-1.805-.245-2.228-.408a3.736 3.736 0 0 1-1.382-.895a3.695 3.695 0 0 1-.9-1.378c-.165-.423-.363-1.058-.417-2.228c-.06-1.264-.072-1.644-.08-4.848c-.006-3.204.006-3.583.061-4.848c.05-1.169.246-1.805.408-2.228c.216-.561.477-.96.895-1.382a3.705 3.705 0 0 1 1.379-.9c.423-.165 1.057-.361 2.227-.417c1.265-.06 1.644-.072 4.848-.08c3.203-.006 3.583.006 4.85.062c1.168.05 1.804.244 2.227.408c.56.216.96.475 1.382.895c.421.42.681.817.9 1.378c.165.422.362 1.056.417 2.227c.06 1.265.074 1.645.08 4.848c.005 3.203-.006 3.583-.061 4.848c-.051 1.17-.245 1.805-.408 2.23c-.216.56-.477.96-.896 1.38a3.705 3.705 0 0 1-1.378.9c-.422.165-1.058.362-2.226.418c-1.266.06-1.645.072-4.85.079c-3.204.007-3.582-.006-4.848-.06m9.783-16.192a1.44 1.44 0 1 0 1.437-1.442a1.44 1.44 0 0 0-1.437 1.442M5.839 12.012a6.161 6.161 0 1 0 12.323-.024a6.162 6.162 0 0 0-12.323.024M8 12.008A4 4 0 1 1 12.008 16A4 4 0 0 1 8 12.008" />
            </svg></a>
          ],

        </div>

      </aside>
      <section class="flex flex-col gap-8 w-full ">


        <article class="@container">
          <h2 class="text-2xl font-bold">Featured Projects</h2>
          <div class="divide-y">
            <div class="p-4 flex flex-col lg:flex-row gap-4 " v-for="project in projects" :key="project.title">
              <div class="flex-1">
                <a :href="project.url" class="hover:opacity-50">
                  
                  <h3 class="text-lg font-medium  lg:text-xl">{{ project.title }}</h3>
                </a>
                
                <p class="mt-2 text-gray-800  ">{{ project.description }}</p>
              </div>
              <a :href="project.url" class="max-w-56 hover:opacity-50">
                <img :src="project.image" alt="Andrew Lucas" class="rounded-lg w-full border" />
              </a>
            </div>
          </div>
        </article>


        <article>
          <h2 class="text-2xl font-bold">Work Experience</h2>
          <div class="divide-y">
            <div class="p-4 flex gap-4" v-for="experience in experiences" :key="experience.company">
              <div>
                <h3 class="text-xl font-medium">{{ experience.company }}</h3>
                <h4 class="text-md text-gray-700">{{ experience.role }} - {{ experience.date }}</h4>
                <p class="mt-2 text-gray-800">
                  {{ experience.description }}
                </p>
              </div>
            </div>
          </div>
        </article>


      </section>

    </main>
  </div>
</template>

<script setup>
const profile = 'andrew.jpeg'

const about = [
  `I am a software engineer fascinated by building fascinating things. Currently working at MIT FutureTech, I have great experience in web development and data visualization.`,
  `When I am not in front of a computer, I like to travel, play chess, hike and go to the beach.`
]

const email = 'andrewlucasgs꩜gmail.com'

const socials = {
  github: 'https://github.com/andrewlucasgs',
  linkedin: 'https://www.linkedin.com/in/andrew-lucas-guedes-de-souza-218192120/',
  twitter: 'https://twitter.com/andrewlucasgs',
  instagram: 'https://www.instagram.com/andrewguedes/'
}

const projects = [
  {
    title: 'Quantum Economic Advantage Calculator',
    description: 'A calculator that helps you understand the economic advantage of quantum computing over classical computing.',
    image: 'quantum-economic-advantage-calculator.png',
    url: 'https://futuretech.mit.edu/quantum-economic-advantage-calculator'
  },
  {
    title: 'Algorithm Wiki',
    description: 'Algorithm Wiki is a database of algorithms and their historical origins. The platform covers a variety of analysis, including the growth of algorithms and their impacts across industries.',
    image: 'algorithmwiki.png',
    url: 'https://algorithm-wiki.netlify.app/'
  },
  {
    title: 'Computer Progress',
    description: 'A website that helps users visualize and understand the economic and technical foundations of computing. The site features interesting visualizations of progress in several computing tasks.',
    image: 'computerprogress.png',
    url: 'https://computerprogress.com/'
  }
]

const experiences = [
  {
    company: 'MIT FutureTech',
    role: 'Software Engineer',
    date: '05/2022 - Present',
    description: `While working at MIT FutureTech, I have been involved in multiple projects such as the Quantum Economic Advantage Calculator, Algorithm Wiki, and Computer Progress. Additionally, I am responsible for maintaining the lab's website. Through my work, I constantly strive to improve the presentation of our research to the public, creating visually appealing data visualizations.`
  },
  {
    company: 'RuaDois',
    role: 'Software Engineer',
    date: '06/2020 - 05/2022',
    description: `At RuaDois, I was a key contributor to the development of the company's main product, a platform designed to help real estate companies become more efficient. My responsibilities included designing and implementing new features in both the frontend and backend of the platform. We were able to increase the number of users and expand the company's area of operation. Additionally, I provided mentorship to junior developers on the team.`
  },
  {
    company: 'Beiramar Imóveis',
    role: 'Software Engineer',
    date: '07/2019 - 01/2021',
    description: `While working at Beiramar, I successfully migrated an old, slow application to a modern property portal, ensuring optimal performance and scalability. Also I was responsible for maintaining and improving their properties portal.`
  },
  {
    company: 'Front',
    role: 'Frontend Engineer',
    date: '01/2019 - 08/2019',
    description: `During my early professional experience as a software engineer, I was primarily responsible for developing the front-end of my company's landing pages and e-commerce platform. Despite facing numerous challenges, I successfully implemented various features and was able to deploy the platform within a period of just 8 months, despite being the only frontend developer working on the project.`
  }
]


</script>