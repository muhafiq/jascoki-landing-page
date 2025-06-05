<script>
  const testimonials = [
    {
      photo: "https://i.pravatar.cc/150?img=12",
      name: "Roland",
      role: "pengguna",
      review: "Saya sangat puas dengan layanan yang diberikan.",
    },
    {
      photo: "https://i.pravatar.cc/150?img=25",
      name: "Ajeng",
      role: "pengguna",
      review:
        "Promo yang diberikan sangat menarik, saya dapat gratis revisi sepuasnya.",
    },
    {
      photo: "https://i.pravatar.cc/150?img=2",
      name: "Afiq",
      role: "pengguna",
      review: "Harga terjangkau dan hasil design sangat memuaskan.",
    },
  ];
</script>

<section class="bg-blue-100 py-16 px-6 flex flex-col items-center">
  <h2 class="text-3xl md:text-4xl font-bold text-center mb-12">Testimoni</h2>

  <div
    class="w-full flex md:justify-center overflow-x-auto md:overflow-visible gap-6 scroll-smooth snap-x md:snap-none"
  >
    {#each testimonials as t}
      <div
        class="min-w-[80%] md:min-w-[300px] md:max-w-[300px] bg-white rounded-2xl p-6 flex flex-col items-center text-center shadow-md snap-center"
      >
        <img
          src={t.photo}
          alt={t.name}
          class="w-24 h-24 object-cover rounded-full mb-4"
        />
        <h3 class="font-semibold">
          {t.name} <span class="text-gray-500 text-sm">({t.role})</span>
        </h3>
        <p class="mt-2 text-sm text-gray-700 italic">"{t.review}"</p>
      </div>
    {/each}
  </div>
</section>
