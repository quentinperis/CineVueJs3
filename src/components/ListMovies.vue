<template>
  <div class="container">
    <h1>Ma Page Cinéma en Vuejs3</h1>
    <div class="liste-films">
      <div v-for="(film, index) in films" :key="index" class="carte-film">
        <img :src="film.imageUrl" :alt="film.title" class="image-film" />
        <h3>{{ film.title }}</h3>
        <button @click="toggleVu(index)" :class="{ vu: film.estVu, 'pas-vu': !film.estVu }">
          {{ film.estVu ? 'Pas vu' : 'Vu' }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive } from 'vue'

export default {
  setup() {
    const films = reactive([
      {
        title: 'Bad Boys for life',
        imageUrl: 'https://fr.web.img6.acsta.net/pictures/19/11/22/09/44/3027567.jpg',
        estVu: true
      },
      {
        title: 'Titanic',
        imageUrl:
          'https://m.media-amazon.com/images/M/MV5BMDdmZGU3NDQtY2E5My00ZTliLWIzOTUtMTY4ZGI1YjdiNjk3XkEyXkFqcGdeQXVyNTA4NzY1MzY@._V1_FMjpg_UX1000_.jpg',
        estVu: false
      },
      {
        title: 'Baby Driver',
        imageUrl:
          'https://m.media-amazon.com/images/M/MV5BMjM3MjQ1MzkxNl5BMl5BanBnXkFtZTgwODk1ODgyMjI@._V1_.jpg',
        estVu: true
      },
      {
        title: 'Medellin',
        imageUrl: 'https://fr.web.img3.acsta.net/pictures/23/05/12/09/06/0196579.jpg',
        estVu: false
      },
      {
        title: 'Le Dernier Jaguar',
        imageUrl: 'https://fr.web.img6.acsta.net/img/a8/4e/a84e320c6740a179bff414694c274401.jpg',
        estVu: true
      },
      {
        title: 'Ocean Eleven',
        imageUrl: 'https://media.senscritique.com/media/000019184318/0/ocean_s_eleven.jpg',
        estVu: false
      },
      {
        title: 'Old Boy',
        imageUrl: 'https://fr.web.img6.acsta.net/pictures/24/02/01/17/31/4129454.jpg',
        estVu: true
      },
      {
        title: 'Le Loup de Wall Street',
        imageUrl: 'https://fr.web.img6.acsta.net/pictures/210/604/21060483_20131125114549726.jpg',
        estVu: false
      },
      {
        title: 'Pablo Escobar',
        imageUrl: 'https://fr.web.img6.acsta.net/pictures/18/03/08/17/46/5852461.jpg',
        estVu: true
      },
      {
        title: 'Furiosa',
        imageUrl:
          'https://m1.quebecormedia.com/emp/emp/furiosa_a_mad_max_saga_affiche_en0f141381-e07b-43ae-a456-b5e8c2802982_ORIGINAL.jpg?impolicy=crop-resize&x=0&y=0&w=1080&h=1600&width=925',
        estVu: false
      },
      {
        title: 'planète des singes',
        imageUrl:
          'https://img-4.linternaute.com/EeH0zA-IMPcoQEPEJoO4ZHbGYW0=/1240x/d53bb38b53724b76b74e5b97fde8f14e/ccmcms-linternaute/224794.jpeg',
        estVu: true
      },
      {
        title: 'Sur les chemins noirs',
        imageUrl:
          'https://image.over-blog.com/2iVQpOAaS6hpE7TTebUAGYB1GQI=/filters:no_upscale()/image%2F0953084%2F20230913%2Fob_88262f_1043282.jpg',
        estVu: false
      },
      {
        title: 'BrickLayer',
        imageUrl:
          'https://static1.colliderimages.com/wordpress/wp-content/uploads/2024/01/the-bricklayer-film-poster.jpg',
        estVu: true
      },
      {
        title: 'Le Gardien',
        imageUrl: 'https://img7.cdn.cinoche.com/images/8579cde48ee1a0cd2cbba7d943738861.jpg',
        estVu: false
      },
      {
        title: 'Quelques jours pas plus',
        imageUrl: 'https://fr.web.img6.acsta.net/pictures/24/03/05/16/04/4544069.jpg',
        estVu: true
      },
      {
        title: 'Le cascadeur',
        imageUrl: 'https://img4.cdn.cinoche.com/images/6d1cf25a1fd34570b3de15394405a539.jpg',
        estVu: false
      },
      {
        title: 'Pathan 2',
        imageUrl:
          'https://cdn.siasat.com/wp-content/uploads/2024/02/Snapinsta.app_429173158_1435251557081048_5381113590930485882_n_1080-819x1024.jpg',
        estVu: true
      },
      {
        title: 'Bob Marley One Love',
        imageUrl:
          'https://www.tribute.ca/news/wp-content/uploads/2024/02/bob_marley_one_love_ver3_xlg.jpg',
        estVu: false
      },
      {
        title: 'Elyas',
        imageUrl: 'https://fr.web.img6.acsta.net/img/d0/98/d098a7d3e8e1173ff37cd11aeef6c259.jpg',
        estVu: true
      },
      {
        title: 'ici et là-bas',
        imageUrl: 'https://medias.unifrance.org/medias/18/55/276242/format_page/here-there.jpg',
        estVu: false
      },
      {
        title: 'Silence',
        imageUrl: 'https://cinedweller.com/wp-content/uploads/2019/11/silence-affiche-scorsese.jpg',
        estVu: true
      },
      {
        title: 'The Revenant',
        imageUrl: 'https://fr.web.img3.acsta.net/pictures/15/11/10/09/30/165611.jpg',
        estVu: false
      },
      {
        title: 'The Aviator',
        imageUrl:
          'https://www.ecranlarge.com/content/uploads/2020/08/qb1ofgndyetiealmw1vtfzqlgfo-249-scaled.jpg',
        estVu: true
      },
      {
        title: 'Equalizer 3',
        imageUrl: 'https://fr.web.img3.acsta.net/pictures/23/06/08/11/11/3391026.jpg',
        estVu: false
      },
      {
        title: 'John Q',
        imageUrl:
          'https://resizing.flixster.com/-XZAfHZM39UwaGJIFWKAE8fS0ak=/v3/t/assets/p29423_p_v13_ag.jpg',
        estVu: true
      },
      {
        title: 'Man of Fire',
        imageUrl: 'https://m.media-amazon.com/images/I/81+6w68Xu0L._AC_UF1000,1000_QL80_.jpg',
        estVu: false
      },
      {
        title: 'Inside Man',
        imageUrl:
          'https://resizing.flixster.com/aRVnhkhyMVNpfLYSMIUhdBmZWcI=/ems.cHJkLWVtcy1hc3NldHMvbW92aWVzL2I1NTkzYzZkLWM5ZGUtNGVmZi1hMjE0LTIwNTkzYWRkNjA0NC53ZWJw',
        estVu: true
      },
      {
        title: 'Hitch',
        imageUrl:
          'https://www.ecranlarge.com/content/uploads/2020/08/d3b1doh9yalr8ruel13yl93mmkb-038.jpg',
        estVu: false
      },
      {
        title: 'Diversion',
        imageUrl:
          'https://media.services.cinergy.ch/media/box1600/e81902d60131911d58e80db10c50cb7c14bfe411.jpg',
        estVu: true
      },
      {
        title: "la loi et l'ordre",
        imageUrl:
          'https://m.media-amazon.com/images/M/MV5BMDdmZGU3NDQtY2E5My00ZTliLWIzOTUtMTY4ZGI1YjdiNjk3XkEyXkFqcGdeQXVyNTA4NzY1MzY@._V1_FMjpg_UX1000_.jpg',
        estVu: false
      }
    ])

    const toggleVu = (index) => {
      films[index].estVu = !films[index].estVu
    }

    return { films, toggleVu }
  }
}
</script>

<style scoped>
.vu {
  background-color: #7da75d;
  color: white;
}

.pas-vu {
  background-color: #123725;
  color: white;
}
h1 {
  text-align: center;
}
.container {
  margin: auto;
  width: 100%;
  height: 600px;
}
.liste-films {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
  padding: 0 20px;
  box-sizing: border-box;
}
h1 {
  color: #f3f3f3;
}

@keyframes borderGlow {
  0% {
    border-color: rgba(195, 230, 119, 0.5);
  }
  50% {
    border-color: rgba(243, 243, 243, 0.8);
  }
  100% {
    border-color: rgba(195, 230, 119, 0.5);
  }
}

.carte-film {
  border: 1px solid rgba(195, 230, 119, 0.3);
  border-radius: 16px;
  padding: 16px;
  width: 250px;
  text-align: center;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 400px;
  transition:
    transform 0.3s ease-in-out,
    box-shadow 0.3s ease-in-out;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
}

.carte-film:hover {
  transform: scale(1.08) rotate(1deg);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
  animation: borderGlow 1.5s infinite;
}

.image-film {
  width: 100%;
  height: 350px;
  border-radius: 12px;
  object-fit: cover;
  transition: transform 0.3s ease-in-out;
}

.carte-film:hover .image-film {
  transform: scale(1.05);
}

button {
  padding: 10px 20px;
  border: none;
  background-color: #007bff;
  color: white;
  border-radius: 8px;
  cursor: pointer;
  position: absolute;
  bottom: 16px;
  left: 50%;
  transform: translateX(-50%);
  transition:
    background-color 0.3s ease-in-out,
    box-shadow 0.3s ease-in-out;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

button:hover {
  background-color: #0056b3;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
}
</style>
