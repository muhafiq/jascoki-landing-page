<script>
  import Counter from "../components/Counter.svelte";
  import Layout from "../components/Layout.svelte";
  import { CircleCheck, PenTool, Flag } from "@lucide/svelte";
  import front from "../assets/front.svg";
  import back from "../assets/back.svg";
  import bgGraphic from "../assets/bg-graphic.jpg";
  import bgCw from "../assets/bg-cw.jpg";
  import nobita from "../assets/gibran-yapping.png";
  import Testimonial from "../components/home/Testimonial.svelte";

  const features = [
    { text: "Gratis Revisi Selamanya" },
    { text: "Layanan 24 Jam" },
    { text: "Harga Terjangkau" },
    { text: "Sesuai Target Pasar" },
  ];

  const whys = [
    { text: "Proyek Diselesaikan", stat: 4000, plus: true },
    { text: "Pengguna Puas", stat: 4000, plus: true },
    { text: "Star Rating", stat: 4.8, plus: false },
  ];

  const services = [
    { text: "Graphic Design", icon: PenTool, bg: bgGraphic },
    { text: "Copywriting", icon: Flag, bg: bgCw },
  ];
</script>

<Layout>
  <!-- hero section -->
  <section
    style="background-image: url('/background.jpg');"
    class="min-h-screen bg-cover bg-center relative z-10"
  >
    <div class="absolute w-full h-screen top-0 left-0 bg-secondary/60"></div>
    <div
      class="flex px-8 py-24 lg:px-32 h-screen w-full items-center text-base-1 relative z-20"
    >
      <div>
        <h1
          class="text-4xl lg:text-6xl font-bold max-w-xl lg:max-w-2xl mb-2 lg:mb-4"
        >
          Desain Keren & Copywriting Tajam untuk Bisnismu!
        </h1>
        <p class="max-w-xl mb-8">
          Kami bantu bisnismu tampil profesional dan menjual di dunia digital.
        </p>
        <a
          href="/#order-now"
          class="bg-transparent px-6 py-3 rounded-md border-2 border-base-1 hover:bg-primary duration-300 font-semibold"
          >Pesan Sekarang</a
        >
      </div>
    </div>
    <!-- features -->
    <div
      class="absolute bg-transparent top-full transform -translate-y-1/2 w-full flex justify-center items-stretch z-30"
    >
      <div
        class="w-full md:max-w-7xl grid grid-cols-2 sm:grid-cols-2 md:grid-cols-4 gap-2 text-xs px-4 text-center"
      >
        {#each features as f}
          <div
            class="p-1 bg-white rounded-md shadow h-full transform md:hover:-translate-y-4 transition-all duration-300 md:hover:shadow-lg shadow-secondary"
          >
            <div
              class="rounded px-4 py-6 lg:py-12 relative border-2 h-full flex flex-col justify-between border-primary"
            >
              <CircleCheck
                class="absolute bottom-full translate-y-1/2 left-1/2 -translate-x-1/2 bg-white w-8 h-8 md:w-12 md:h-12 text-primary rounded-full"
              />
              <p class="text-xs font-bold md:text-lg">{f.text}</p>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
  <!-- end of hero section -->

  <!-- why section -->
  <section
    class="min-h-screen bg-base-2 flex flex-col items-center justify-center pt-28 pb-20 px-8"
  >
    <h1 class="font-bold text-2xl md:text-4xl mb-8 md:mb-24">
      Kenapa Memilih Kami?
    </h1>
    <div
      class="flex flex-col items-center gap-8 md:gap-16 lg:gap-48 md:flex-row md:border-b-4 md:border-base-1 md:pb-8"
    >
      {#each whys as w}
        <div class="flex flex-col gap-2 items-center">
          <Counter target={w.stat} plus={w.plus} />
          <p class="text-lg md:text-2xl text-center font-bold">{w.text}</p>
        </div>
      {/each}
    </div>
  </section>
  <!-- end of why section -->

  <!-- Layanan -->
  <section
    id="services"
    class="min-h-screen bg-base-2 flex flex-col items-center p-8"
  >
    <h1 class="font-bold text-2xl md:text-4xl mb-8 md:mb-20">Layanan Kami</h1>
    <div
      class="grid grid-cols-1 md:grid-cols-2 gap-4 md:gap-12 lg:gap-24 mb-20"
    >
      {#each services as s}
        <div class="bg-blue-200 rounded-md p-2 relative shadow">
          <img src={s.bg} alt={s.text} loading="lazy" class="w-80" />
          <svelte:component
            this={s.icon}
            class="absolute -top-2 -left-2 bg-base-1 rounded-full p-2 md:p-3 text-primary w-12 h-12"
          />
          <img src={back} alt="Back" class="absolute bottom-0 left-0" />
          <img src={front} alt="Front" class="absolute bottom-0 left-0" />
          <p class="absolute bottom-6 left-6 text-lg md:text-2xl font-bold">
            {s.text}
          </p>
        </div>
      {/each}
    </div>
    <!-- promo -->
    <div
      class="lg:min-w-4xl md:min-w-2xl min-w-sm px-8 md:py-12 bg-cover bg-center text-center text-base-1 relative rounded-lg"
      style="background-image: url('/andong.png');"
    >
      <div
        class="absolute lg:min-w-4xl md:min-w-2xl min-w-sm h-full bg-secondary/60 rounded-lg top-0 left-0"
      ></div>
      <div class="relative z-10">
        <h1 class="font-bold text-3xl mb-2">Promo Hari Merdeka</h1>
        <p>Berlaku mulai 17 Agustus sampai 24 Agustus 2025</p>
      </div>
      <img
        src={nobita}
        alt="Semangat Merdeka"
        class="absolute right-0 bottom-0 h-full"
      />
      <div
        class="absolute w-24 h-24 top-[calc(100%-4rem)] -left-6 inset-0 bg-red-500 text-white font-bold text-sm flex items-center justify-center transform -rotate-30 clip-starburst"
      >
        17% OFF
      </div>
      <button
        class="absolute right-1/2 -bottom-5 translate-x-1/2 px-4 py-2 rounded-md bg-base-1 text-accent shadow text-xs md:text-base"
        >Kode Promo: <span class="text-red-500 font-bold">MERDEKA</span>
      </button>
    </div>
  </section>
  <!-- end of Layanan -->

  <!-- testimoni -->
  <Testimonial />

  <section
    id="order-now"
    class="bg-cover bg-center text-center py-48 px-4 relative"
    style="background-image: url('/landscape.jpg');"
  >
    <div class="absolute w-full h-full bg-base-2/50 top-0 left-0"></div>
    <h2 class="text-3xl md:text-5xl font-bold text-black mb-8 relative z-10">
      Buat Desainmu Lebih Menarik<br />
      Sekarang Juga!
    </h2>
    <a
      href="https://wa.me/6289519417756"
      class="inline-block relative z-10 bg-primary text-base-1 font-medium text-lg md:text-xl px-8 py-4 rounded-lg shadow hover:bg-secondary transition"
    >
      Chat Admin
    </a>
  </section>
</Layout>

<style>
  .clip-starburst {
    clip-path: polygon(
      50% 0%,
      58% 12%,
      71% 5%,
      74% 19%,
      87% 13%,
      86% 27%,
      100% 30%,
      90% 41%,
      100% 50%,
      90% 59%,
      100% 70%,
      86% 73%,
      87% 87%,
      74% 81%,
      71% 95%,
      58% 88%,
      50% 100%,
      42% 88%,
      29% 95%,
      26% 81%,
      13% 87%,
      14% 73%,
      0% 70%,
      10% 59%,
      0% 50%,
      10% 41%,
      0% 30%,
      14% 27%,
      13% 13%,
      26% 19%,
      29% 5%,
      42% 12%
    );
  }
</style>
