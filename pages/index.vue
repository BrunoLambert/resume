<template>
  <v-layout row wrap>
    <v-flex xs12 md4 xl3 pa-3 class="side-col">
      <h1 class="hidden-md-and-up">
        Bruno Fonseca Lambert
      </h1>
      <p class="hidden-md-and-up mb-5">
        Desenvolvedor em crescimento, almejando cada vez mais o sucesso e se especializando em tecnologias de frontend.
      </p>
      <v-img src="/profile.jpg" class="profile-photo" />
      <div class="mt-5">
        <h2>Contato</h2>
        <p>E-mail: brunofsclambert@gmail.com</p>
        <p>Telefone: (11) 94856-0966</p>
      </div>
      <div class="mt-5">
        <h2>Principais habilidades</h2>
        <v-layout row wrap mx-1>
          <v-flex v-for="skill in skills.slice(0,6)" :key="skill" xs6 md4 mb-1>
            {{ skill }}
          </v-flex>
        </v-layout>
      </div>
      <div class="mt-5">
        <h2>Idiomas</h2>
        <p>Português (nativo)</p>
        <p>Inglês (avançado)</p>
        <p>Espanhol (iniciante)</p>
      </div>
      <div class="mt-5">
        <h2>Conhecimentos</h2>
        <p v-for="knowledge in knowledges" :key="knowledge">
          {{ knowledge }}
        </p>
      </div>
      <div class="mt-5">
        <h2>Outras habilidades</h2>
        <v-layout row wrap mx-1>
          <v-flex v-for="skill in skills.slice(6)" :key="skill" class="mb-1 mr-2">
            {{ skill }}
          </v-flex>
        </v-layout>
      </div>
      <div class="mt-5">
        <h2>Projetos</h2>
        <a v-for="(project, index) in projects" :key="index" :href="project.link" target="_blank" class="no-underline">
          <v-layout row wrap class="mx-1 my-4 project-layout">
            <v-flex xs12>
              <h4>{{ project.name }}</h4>
            </v-flex>
            <v-flex xs12>
              <small>{{ project.description }}</small>
            </v-flex>
            <v-flex xs12 mb-3>
              <b><small>{{ project.period }}</small></b>
            </v-flex>
          </v-layout>
        </a>
      </div>
    </v-flex>
    <v-flex xs12 md8 xl9 pa-3 class="dark--text main-col">
      <h1 class="hidden-sm-and-down">
        Bruno Fonseca Lambert
      </h1>
      <p class="hidden-sm-and-down">
        Desenvolvedor em crescimento, almejando cada vez mais o sucesso e se especializando em tecnologias de frontend.
      </p>
      <div class="mt-5">
        <h2>Experiências Profissionais</h2>
        <v-layout v-for="(experience, index) in experiencies" :key="index" row wrap class="mx-2 mb-10 mt-4">
          <v-flex xs12>
            <h4> {{ experience.role }}</h4>
          </v-flex>
          <v-flex xs12>
            <small>{{ experience.startedAt }} ~ {{ experience.leftAt }}</small>
          </v-flex>
          <v-flex xs12>
            <p>{{ experience.description }}</p>
          </v-flex>
          <v-flex xs10 md3 class="experience-line my-2" />
          <v-flex xs12>
            <b><small>{{ experience.company }} - {{ experience.location }}</small></b>
          </v-flex>
        </v-layout>
      </div>
      <div class="mt-5">
        <h2>Educação</h2>
        <v-layout v-for="(education, index) in educations" :key="index" row wrap class="mx-2 mb-10 mt-4">
          <v-flex xs12>
            <h4> {{ education.school }}</h4>
          </v-flex>
          <v-flex xs12>
            <small>{{ education.startedAt }} ~ {{ education.finishedAt }}</small>
          </v-flex>
          <v-flex xs12>
            <p>{{ education.degree }}</p>
          </v-flex>
          <v-flex xs12>
            <b><small>{{ education.location }}</small></b>
          </v-flex>
        </v-layout>
      </div>
      <div class="mt-5">
        <h2>Perfis</h2>
        <v-layout row wrap mx-3 mt-4>
          <v-flex v-for="link in links" :key="link.title" xs12 mb-5 class="text-center text-md-left">
            <v-icon :class="link.iconClass" class="mr-3">
              {{ link.icon }}
            </v-icon>
            <b>{{ link.title }}: <a :href="link.url" target="_blank">{{ link.url }}</a></b>
          </v-flex>
          <v-flex xs12 mb-5 class="text-center text-md-left">
            <v-icon class="mr-3 whatsapp-icon">
              fab fa-whatsapp-square
            </v-icon>
            <b>Whatsapp: <a href="https://api.whatsapp.com/send?phone=5511948560966" target="_blank">+55 11 94856-0966</a></b>
          </v-flex>
          <v-flex xs12 mb-5 class="text-center text-md-left">
            <v-icon class="mr-3 skype-icon">
              fab fa-skype
            </v-icon>
            <b>Skype: brunoflambert</b>
          </v-flex>
        </v-layout>
      </div>
      <div class="mt-5 mb-3">
        <h2>Curiosidades</h2>
        <v-layout row wrap mx-3 mt-4>
          <v-flex xs12>
            <p>Interesse em morar em São Paulo, Porto Alegre, Florianópolis</p>
          </v-flex>
          <v-flex xs12>
            <p>Interesse em aperfeiçoar idomas (Inglês e Espanhol)</p>
          </v-flex>
          <v-flex xs12>
            <p>Streamer nas horas vagas (<a href="https://www.twitch.tv/boruntw" target="_blank">Twitch</a> / <a href="https://www.youtube.com/channel/UCzhSb2qjPx3GPxnKzs0s02A" target="_blank">YouTube</a> - Boruntw)</p>
          </v-flex>
        </v-layout>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  head: {
    title: 'Bruno Fonseca Lambert'
  },
  data: () => ({
    skills: [
      'Vue.js',
      'React.js',
      'React Native',
      'HTML5',
      'CSS',
      'JavaScript',
      'SASS',
      'Nuxt.js',
      'Next.js',
      'Redux.js',
      'Vuetify.js',
      'Laravel',
      'Ruby on Rails',
      'Rest API',
      'MySQL',
      'PostgreSQL',
      'Material Design',
      'Git'
    ],
    knowledges: [
      'Desenvolvimento Frontend',
      'Desenvolvimento Backend',
      'User Experience (UX)',
      'User Interface (UI)',
      'Aplicações Web',
      'Design Patterns',
      'Design Responsivo',
      'Metodologias Ágeis (SCRUM, KANBAN)'
    ],
    projects: [
      {
        name: 'Optclips',
        description: 'Sistema de gestão para advogados (B2C), mapeando os clips de acordo com o perfil em diários por todo o Brasil.',
        period: 'Agosoto 2020 ~ Atualmente',
        link: 'https://optclips.com.br/',
        company: 'Optimum Soluções'
      },
      {
        name: 'Plataforma Optimum',
        description: 'Projeto de análises relacionados a processos jurídicos (B2B).',
        period: 'Fevereiro 2020 ~ Atualmente',
        link: 'https://www.optimumsolucoes.com/',
        company: 'Optimum Soluções'
      },
      {
        name: 'Code Adventure',
        description: 'Projeto iniciado na Rocketseat Experience 2019 com objetivo de atrair novos aspirantes da computação.',
        period: 'Novembro 2019',
        link: 'https://codeadventure.app/',
        company: null
      },
      {
        name: 'JobShop - UNIFEI JR',
        description: 'Apresentação e cadastro para o evento realizado pela Unifei JR.',
        period: 'Agosto 2019',
        link: 'https://jobshop.unifeijr.com.br/',
        company: 'Incluir Tecnologia - Itajubá MG'
      },
      {
        name: 'MOVA',
        description: 'O 1º Peer-to-Peer Lending aprovado pelo Banco Central no formato de SEP.',
        period: 'Abril 2019 ~ Agosto 2019',
        link: 'https://mova.vc/',
        company: 'Incluir Tecnologia - Itajubá MG'
      },
      {
        name: 'TAprint',
        description: 'Plataforma de vendas de impressões 3D.',
        period: 'Janeiro 2019 ~ Julho 2019',
        link: 'https://www.taprint.com.br/',
        company: 'Incluir Tecnologia - Itajubá MG'
      },
      {
        name: 'Libras Texto',
        description: 'Plataforma de tradução: texto para libras (video) ou libras para texto.',
        period: 'Junho 2019',
        link: 'https://libras.incluirtecnologia.com.br/',
        company: 'Incluir Tecnologia - Itajubá MG'
      },
      {
        name: 'Curso Libras',
        description: 'Site para divulgação e inscrição do curso de libras oferecido pela empresa Incluir Tecnologia.',
        period: 'Março 2019',
        link: 'https://cursolibras.incluirtecnologia.com.br/',
        company: 'Incluir Tecnologia - Itajubá MG'
      },
      {
        name: 'Inclur Tecnologia',
        description: 'Site de divulgação da empresa Incluir Tecnologia.',
        period: 'Dezembro 2018 ~ Fevereiro 2019',
        link: 'https://www.incluirtecnologia.com.br/',
        company: 'Incluir Tecnologia - Itajubá MG'
      },
      {
        name: 'Tuuris.com',
        description: 'Conectando viajantes às agências de viagem de forma fácil e rápida.',
        period: 'Novembro 2017 ~ Outubro 2018',
        link: 'https://tuuris.com/',
        company: 'Tuuris - Itajubá MG'
      }
    ],
    experiencies: [
      {
        role: 'Desenvolvedor Frontend Web',
        company: 'Optimum Soluções',
        description: 'Desenvolvimento frontend usando Vue/NuxtJs integrado com APIs, desenvolvimento sistemas de anaálises de processos jurídicos (Plataforma Optimum - B2B) e captando informações sobre as atividades de advogados cadastrados (OptClips - B2C) .',
        startedAt: 'Fevereiro 2020',
        leftAt: 'Atualmente',
        location: 'São Paulo - SP'
      },
      {
        role: 'Desenvolvedor Frontend Web',
        company: 'Beeleads',
        description: 'Desenvolvimento frontend usando ReactJS, NextJS and Reac Native. Principal desenvolvimento: https://www.bigtester.com.br/',
        startedAt: 'Agosto 2019',
        leftAt: 'Janeiro 2020',
        location: 'Itajubá - MG'
      },
      {
        role: 'Estagiário de Desenvolvimento Web',
        company: 'Incluir Tecnologia',
        description: 'Desenvolvimento Frontend Web usando VueJS, NextJS. Também desenvolvendo quando necessário o backend, usando PHP, Laravel e MySQL.',
        startedAt: 'Dezembro 2018',
        leftAt: 'Agosto de 2019',
        location: 'Itajubá - MG'
      },
      {
        role: 'Estagiário de Desenvolvimento Web',
        company: 'Tuuris',
        description: 'Desenvolvimento web usando JavaScript (Node.JS - Vue/Nuxt - Vuetify), Ruby (Rails) and MySQL (BD). Focando em desenvolver o site Tuuris.com que conecta os viajantes as agências de viagens.',
        startedAt: 'Novembro 2017',
        leftAt: 'Outubro de 2018',
        location: 'Itajubá - MG'
      },
      {
        role: 'Técnico de Informática',
        company: 'FAI - Centro de Ensino Superior em Gestão, Tecnologia e Educação',
        description: 'Suporte de informática, físico e software, nos setores administrativos e laboratórios de estudos. Manutenção de redes, suporte a alunos e professores.',
        startedAt: 'Fevereiro 2014',
        leftAt: 'Outubro de 2015',
        location: 'Santa Rita do Sapucaí - MG'
      },
      {
        role: 'Técnico de Desenvolvimento de Produtos',
        company: 'Intelbras',
        description: 'Desenvolvimento de alarmes internos e externos, assim como testes dos protótipos em campo. Comunicação em inglês e espanhol com parceiros de negócio da empresa.',
        startedAt: 'Setembro 2013',
        leftAt: 'Fevereiro de 2014',
        location: 'Santa Rita do Sapucaí - MG'
      },
      {
        role: 'Estágio de Tecnico de Eletrônica',
        company: 'TST Telmax Soluções em Telecomunicações',
        description: 'Homologação de telefonia móvel, criando relatórios em inglês a respeitos dos resultados. Testes em campo e internos dos aparelhos móveis.',
        startedAt: 'Março 2013',
        leftAt: 'Junho de 2013',
        location: 'São Paulo - SP'
      }
    ],
    educations: [
      {
        school: 'UNIFEI - Universidade Federal de Itajubá',
        degree: 'Bacharel - Sistema de Informações',
        startedAt: 'Janeiro 2016',
        finishedAt: '2021',
        location: 'Itajubá - MG'
      },
      {
        school: 'FAI - Centro de Ensino Superior em Gestão, Tecnologia e Educação',
        degree: 'Bacharel - Sistema de Informações',
        startedAt: 'Janeiro 2014',
        finishedAt: 'Dezembro 2015',
        location: 'Santa Rita do Sapucaí - MG'
      },
      {
        school: 'ETE - Escola Técnica de Eletrônica "Francisco Moreira da Costa"',
        degree: 'Técnico de Eletrônica e Telecomunicações',
        startedAt: 'Janeiro 2010',
        finishedAt: 'Dezembro 2012',
        location: 'Santa Rita do Sapucaí - MG'
      }
    ],
    links: [
      {
        title: 'LinkedIn',
        url: 'https://www.linkedin.com/in/brunoflambert/',
        icon: 'fab fa-linkedin',
        iconClass: 'linkedin-icon'
      },
      {
        title: 'Gitlab',
        url: 'https://gitlab.com/bflambert',
        icon: 'fab fa-gitlab',
        iconClass: 'gitlab-icon'
      },
      {
        title: 'Github',
        url: 'https://github.com/BrunoLambert',
        icon: 'fab fa-github-square',
        iconClass: 'github-icon'
      }
    ]
  })
}
</script>

<style scoped>
.side-col {
  background-color: rgba(0, 0, 100, 0.3);
  color: white;
}
.main-col {
  background-color: rgba(0, 0, 100, 0.1);
}
.profile-photo {
  height: 200px;
  width: 200px;
  border-radius: 50%;
  margin: auto;
  border: 5px solid rgba(0, 0, 100, 0.5);
}
.experience-line {
  width: 150px;
  border-bottom: 5px dotted rgba(0, 0, 100, 0.7);
}
.project-layout {
  border-bottom: 5px dotted rgba(0, 0, 100, 0.2);
}
</style>
