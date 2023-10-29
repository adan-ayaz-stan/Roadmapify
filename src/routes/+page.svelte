<script>
  import { page } from "$app/stores";
  import Button from "$lib/components/ui/button/button.svelte";
  import Icon from "@iconify/svelte";

  const data = [
    {
      title: "A world of possibilities",
      description:
        "Unlock the power to effortlessly plan, visualize, and share project roadmaps.",
      icon: "game-icons:burst-blob",
    },
    {
      title: "Quality that you can trust",
      description: "Uncover Roadmapify's Pro-Grade Roadmapping Capabilities.",
      icon: "game-icons:abstract-024",
    },
    {
      title: "Plan and visualize",
      description:
        "Instantaneous Roadmaps: Plan, visualize with unmatched speed.",
      icon: "game-icons:atom-core",
    },
  ];
</script>

<svelte:head>
  <title>Home | Svelte</title>
  <meta name="description" content="Roadmapify" />
</svelte:head>

<section>
  <!-- First Section -->

  <div
    class="min-h-screen relative flex flex-col justify-between pt-12 lg:pt-32"
  >
    <div
      class="h-full grid grid-cols-1 lg:grid-cols-2 auto-rows-fr lg:px-20 md:px-12 sm:px-4 px-2"
    >
      <div class="flex flex-col justify-center gap-8">
        <h1 class="scroll-m-20 text-4xl font-medium tracking-tight lg:text-5xl">
          Discover the joy of <br />
          <span class="text-blue-400 font-bold rounded-xl">effortless</span>
          project timeline <br /> creations with
          <span class="text-blue-400 font-bold rounded-xl">Roadmapify</span>.
        </h1>
        <p class="text-sm text-muted-foreground">
          Redefining Project Planning. Seamlessly create, visualize, and share
          project roadmaps to drive success and exceed expectations in every
          endeavor.
        </p>
      </div>
      <div class="relative flex items-center justify-center">
        <div
          class="absolute inset-0"
          style="background: radial-gradient(circle, rgba(255,255,255,0) 50%, rgba(255,255,255,1) 100%);"
        />

        <img
          src="/images/hero-image.png"
          alt="Polka Dot SVG"
          class="h-[400px] w-[400px] lg:h-[500px] lg:w-[500px] object-cover"
        />
      </div>
    </div>

    <div
      class="group grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 auto-rows-fr gap-[1px] pt-[1px] bg-gray-300 border-b-[1px] border-gray-300"
    >
      <div class="flex items-center justify-center bg-white rounded-tr-md">
        <Button class="rounded-full">Get Started</Button>
      </div>
      {#each data as ele (ele.title)}
        <div
          class="grid grid-cols-6 auto-rows-fr px-4 py-12 gap-4 bg-white last:rounded-tl-md last:rounded-tr-none rounded-t-md"
        >
          <div class="col-span-1 flex items-center justify-center">
            <Icon icon={`${ele.icon}`} width="36" height="36" />
          </div>
          <div class="col-span-5">
            <h2
              class="font-semibold uppercase"
              style="font-family: 'Roboto Slab', serif;"
            >
              {ele.title}
            </h2>
            <p class="text-sm text-muted-foreground">{ele.description}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>

  <!-- Features Section -->
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:text-center">
        <h1
          class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl"
        >
          Project Features
        </h1>
        <p class="mt-6 text-lg leading-8 text-gray-600">
          Effortlessly create, visualize, and share project roadmaps. Input
          stages, add detailed descriptions, and instantly generate stunning
          visual representations of your project timelines.
        </p>
      </div>
      <div class="mx-auto mt-16 max-w-2xl sm:mt-20 lg:mt-24 lg:max-w-4xl">
        <dl
          class="grid max-w-xl grid-cols-1 gap-x-8 gap-y-10 lg:max-w-none lg:grid-cols-2 lg:gap-y-16"
        >
          <div class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-black"
              >
                <Icon
                  icon="game-icons:treasure-map"
                  width="24"
                  height="24"
                  color="white"
                />
              </div>
              Intuitive Roadmap Creation
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              Effortlessly design project roadmaps with an intuitive interface.
              Drag and drop stages, add detailed descriptions, and watch your
              vision come to life.
            </dd>
          </div>
          <div class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-black"
              >
                <Icon
                  icon="game-icons:time-bomb"
                  width="24"
                  height="24"
                  color="white"
                />
              </div>
              Visual Timeline Generation
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              Instantly generate visually captivating timelines that vividly
              represent your project's journey. Impress stakeholders with
              professional-grade graphics.
            </dd>
          </div>
          <div class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-black"
              >
                <Icon
                  icon="carbon:collaborate"
                  width="24"
                  height="24"
                  color="white"
                />
              </div>
              Collaborative Editing
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              Facilitate seamless teamwork. Invite team members to collaborate
              in real-time, ensuring everyone is aligned on project milestones
              and progress.
            </dd>
          </div>
          <div class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-black"
              >
                <Icon
                  icon="game-icons:progression"
                  width="24"
                  height="24"
                  color="white"
                />
              </div>
              Progress Tracking
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              Monitor project progress with precision. Track completed stages,
              identify bottlenecks, and stay on top of critical milestones.
            </dd>
          </div>
          <div class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-black"
              >
                <Icon icon="ph:export" width="24" height="24" color="white" />
              </div>
              Export and Share
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              Easily export your project roadmap in multiple formats. Share with
              clients, stakeholders, or integrate directly into presentations
              and reports.
            </dd>
          </div>
          <div class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-black"
              >
                <Icon
                  icon="mdi:responsive"
                  width="24"
                  height="24"
                  color="white"
                />
              </div>
              Mobile Responsiveness
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              Access and edit your roadmaps on the go. Roadmapify adapts
              seamlessly to different devices, keeping you connected wherever
              you are.
            </dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</section>

<style>
</style>
