<script>
	import { ClockIcon, HardDriveIcon, LockIcon, ShieldIcon, ToolIcon } from "svelte-feather-icons";
	import Icon from "../icon.svelte";

</script>
<!-- Banks Section -->
<section id="offices" class="mb-10 p-2 rounded-lg">
    <h2 class="mb-2 text-2xl font-bold">Offices</h2>
    <p class="mb-8 text-lg">
        Comprehensive IT support and device repair for modern office environments. Keep your teams productive with fast, reliable service and proactive maintenance for all your office technology.
    </p>
    <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
        <!-- Workstation repair -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
           <Icon>
                <i slot="icon"> <HardDriveIcon/> </i>
           </Icon>
            <h3 class="mb-2 text-xl font-bold">WorkStation Repair</h3>
            <p class="mb-4">
                Expert diagnostics and repair for desktops, laptops, and peripherals.
            </p>
            <a
                href="#"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >Request Service</a
            >
        </div>

        <!-- Network Solution -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
        <Icon>
            <i slot="icon"> <ShieldIcon/> </i>
       </Icon>
            <h3 class="mb-2 text-xl font-bold">Network Solutions</h3>
            <p class="mb-4">Setup, troubleshooting, and optimization for office networks and Wi-Fi.</p>
            <a
                href="/Tasmal-X"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >See Features</a
            >
        </div>

        <!-- Preventive Measure -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
        <Icon>
            <i slot="icon"> <ClockIcon/> </i>
       </Icon>
            <h3 class="mb-2 text-xl font-bold">Preventive Measures</h3>
            <p class="mb-4">Scheduled checkups to minimize downtime and extend device lifespan.</p>
            <a
                href="#"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >Learn More</a
            >
        </div>
    </div>
</section>