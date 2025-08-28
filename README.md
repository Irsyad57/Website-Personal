[bucin.html](https://github.com/user-attachments/files/22019226/bucin.html)
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- ganti nama/judul website -->
    <title>Website Bucin - IRR</title>
    <style>
      body {
        /* ganti background website */
        background-image: url(https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT4PzjXeToHTRByQQwFRDKWyyPvqAipbD95YQ&s);
      }
    </style>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
    />
  </head>

  <body class="justify-center flex">
    <main
      class="bg-white rounded mt-24 p-8 shadow-lg shadow-red-200 animate__animated animate__backInDown"
    >
      <!-- ganti gambar awal -->
      <img
        class="cat-img"
        src="https://i.pinimg.com/originals/3c/e8/84/3ce884bb29ad1909a2c253354497420f.gif"
        alt="Picture of a cat"
        width="200"
      />
      <div class="border-b mt-2 border-2"></div>
      <div class="lh-1 text-center mt-4">
        <!-- ganti nama -->
        <h2 class="title text-red-400 text-xl font-semibold">
          Hai haii, haloo izza.
        </h2>
        <!-- ganti pertanyaan -->
        <p class="title question fs-1 text-2xl font-bold text-gray-700">Mau diajak Irsyad beli seblak ngga</p>
      </div>
      <div class="buttons mt-5 flex justify-around">
        <!-- ganti tulisan tombol -->
        <button
          type="button"
          class="btn-yes bg-green-500 rounded text-white text-3xl px-2 pt-1 pb-2 animate__pulse animate__animated animate__infinite"
        >
          yes
        </button>
        <button
          type="button"
          class="btn-no bg-red-500 rounded text-white text-2xl px-2 pt-1 pb-2"
        >
          no
        </button>
      </div>
      <div class="numbers hidden mt-5 flex justify-center">
        <!-- ganti link -->
        <a
          href="https://wa.me/085739206497"
          type="button"
          class="bg-green-500 text-white py-1 px-2 rounded btn-yes w-100 text-xl font-bold"
        >
          <!-- ganti tulisan tombol link -->
          Chat disini</a
        >
      </div>
    </main>

    <script>
      const titleElement = document.querySelector(".title");
      const buttonsContainer = document.querySelector(".buttons");
      const numberContainer = document.querySelector(".numbers");
      const yesButton = document.querySelector(".btn-yes");
      const noButton = document.querySelector(".btn-no");
      const catImg = document.querySelector(".cat-img");
      const title = document.querySelector(".title");
      const question = document.querySelector(".question");

      // jumlah gambar
      const MAX_IMAGES = 5;

      let play = true;
      let count = 0;

      // ganti gambar pake link gif yang kalian mau
      let listGambar = [
        "https://media1.tenor.com/m/BbSkyx3DaEgAAAAd/goma-sad.gif",
        "https://media.tenor.com/M9WbqMQ2ISwAAAAi/annoyed.gif",
        "https://media.tenor.com/oHJdcKei2o0AAAAj/no-no-no.gif",
        "https://i.pinimg.com/originals/e1/64/7b/e1647b7fd330918520b12076a8a2dfcd.gif",
        "https://media1.tenor.com/m/M_5Qg9ok3HQAAAAC/cat-pout.gif",

        // gambar kalo dijawab ya
        "https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExNW9temgzcjlieHJtOXM2YXhoeW94N2k2c3ljcmtpYTZ4NnBicm0ybyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/f9EmXxglhdhAj1bo28/giphy.webp",
      ];

      yesButton.addEventListener("click", handleYesClick);

      noButton.addEventListener("click", function () {
        title.classList.add("hidden");
        question.classList.add("hidden");
        if (play) {
          count++;
          const imageIndex = Math.min(count, MAX_IMAGES);
          changeImage(imageIndex);
          updateNoButtonText();
          if (count === MAX_IMAGES) {
            play = false;
          }
        }
      });

      function handleYesClick() {
        buttonsContainer.classList.add("hidden");
        title.classList.add("hidden");
        question.classList.add("hidden");
        numberContainer.classList.remove("hidden");
        changeImage(6);
      }

      // ganti kata-kata kalo ditolak
      function generateMessage(count) {
        const messages = ["no", "hmm?", "gaboleee", "tak omell", "plis plis", "fiks tak omel"];

        const messageIndex = Math.min(count, messages.length - 1);
        return messages[messageIndex];
      }

      function changeImage(imageIndex) {
        catImg.src = `${listGambar[imageIndex - 1]}`;
      }

      function updateNoButtonText() {
        noButton.innerHTML = generateMessage(count);
      }
    </script>
  </body>
</html>
