<script>
    import Modal from "./Modal.svelte";
    import Step from "./Step.svelte";

    let steps = [
        {
            name: "Encost Smart Graph Project",
            icon: "fa-solid fa-diagram-project",
            briefdescription: `<p>The Encost Smart Graph Project enables the visualization of Encost’s smart devices using a graph data structure. This project was undertaken 
                    as part of a software engineering course at the University of Waikato using <strong class="text-violet-400">Java and GraphStream.</strong></p>`,
            description: `<p>The <strong>Encost Smart Graph Project</strong> (ESGP) is a software system designed to visualise Encost's smart home devices using a graph data 
                    structure. The core functionality of the ESGP revolves around is ability to display devices from the Encost Smart Homes Dataset as nodes in a graph, with their
                    connections represented as edges. This allows users to see how devices are interconnected and whether each device can send and/or receive commands.</p><br>
                    <p>Users of the ESGP are categorised into two roles: Community Users and Encost Users. Community Users have access to the basic feature of viewing the graph
                    visualisation for the Encost Smart Homes Dataset. Encost Users, on the other hand, have access to loading custom datasets, visualising graph representations, 
                    and viewing summary statistics on device distribution, location, and connectivity.</p><br>
                    <p>The software is built on a technology stack that includes Windows 10 as the intended operating system, Java verstion 1.8.0 or higher, and the GraphStream
                        library version 1.3 for building and visualising dynamic graphs. The design of the ESGP follows object-orientated principles.</p><br>
                    <p>Take a further look in the repository below!</p>`,
            image1: "images/ESGPConsole.png",
            image2: "images/ESGPGraph.png",
            repolink: "https://github.com/j3sseO/EncostSmartGraphProject",
        },
        // {
        //     name: "n/a",
        //     icon: "fa-solid fa-diagram-project",
        //     href: "",
        //     image1: "",
        // },
        // {
        //     name: "n/a",
        //     icon: "fa-solid fa-diagram-project",
        //     href: "",
        //     image1: "",
        // },
    ];

    let selectedStep = null;
    let showModal = false;

    function handleStepClick(step) {
        selectedStep = step;
        showModal = true;
    }

    function closeModal() {
        showModal = false;
        selectedStep = null;
    }

    let benefits = [
        {
            name: "An educated professional",
            description:
                "I'm a motivated and detail-orientated final year Computer Science student with a strong foundation in software development, algorithms, data structures, web development, database concepts, and networking.",
        },
        {
            name: "An experienced individual",
            description:
                "I'm experienced in various programming languages including Java, and C#, with a proven ability to design, develop, and implement innovative software solutions",
        },
        {
            name: "An excellent communicator",
            description:
                "Communication is key and it's a paramount value of mine. I believe in transparency and constructive communication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.",
        },
    ];
</script>

<main class="flex flex-col flex-1 p-4">
    <section
        id="introPage"
        class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
    >
        <div
            class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
        >
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span class="poppins text-violet-400">Jesse</span>
                OConnor <br /> Computer Science
                <span class="poppins text-violet-400">Student</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                My <span class="text-violet-400">favourite tech</span> includes JavaScript
                (SvelteKit), TailwindCSS, ...
            </p>
            <a
                href="https://www.linkedin.com/in/jesse-oconnor"
                target="_blank"
                class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:textt-lg md:text-xl poppins
                relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950
                cursor-pointer"
            >
                <div
                    class="absolute top-0 right-full w-full h-full bg-violet-400
                    opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class="relative z-9">Get in touch &rarr;</h4>
            </a>
        </div>
        <div class="relative grid place-items-center">
            <!-- svelte-ignore a11y-img-redundant-alt -->
            <img
                src={"images/profile.png"}
                alt="Profile image"
                class="object-cover z-[2] max-h-[70vh]"
            />
        </div>
    </section>
    <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="ext-large sm:text-xl md:text-2xl">
                Curious to <span class="poppins text-violet-400">see</span> my work?
            </h6>
        </div>
        <a
            href="https://github.com/j3sseO"
            target="_blank"
            class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex
            items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <!-- <i class="fa-regular fa-circle-play"></i> -->
            <p>GitHub</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-10">
            {#each steps as step}
                <Step {step} onClick={() => handleStepClick(step)}>
                    {@html step.briefdescription}
                </Step>
            {/each}
            <h3 class="font-medium text-xl sm:text-2xl md:text-3xl self-center">More to come!</h3>
        </div>
    </section>
    <Modal show={showModal} step={selectedStep} onClose={closeModal} />
    <section
        id="about"
        class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
    >
        <div
            class="flex flex-col gap-2 text-center relative before:absolute before:top-0
        before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0
        after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
        >
            <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                A bit <span class="poppins text-violet-400">about</span> me.
            </h3>
        </div>
        <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
            I am . . .
        </p>
        <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
            {#each benefits as benefit, index}
                <div class="flex gap-6 sm:gap-8">
                    <p
                        class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
                    >
                        0{index + 1}
                    </p>
                    <div class="flex flex-col gap-6 sm:gap-8">
                        <h3 class="text-2xl sm:text-3xl md:text-5xl">
                            {benefit.name}
                        </h3>
                        <p>{benefit.description}</p>
                    </div>
                </div>
            {/each}
        </div>
    </section>
</main>
