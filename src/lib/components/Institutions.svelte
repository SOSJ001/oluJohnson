<script>
	import { BriefcaseIcon, ShieldIcon, SlidersIcon } from "svelte-feather-icons";
	import Icon from "./icon.svelte";


</script>
<!-- Institutions Section -->
<section id="institutions" class="mb-10 bg-purple-200 p-2 rounded-lg">
    <h2 class="mb-2 text-2xl font-bold">Institutions</h2>
    <p class="mb-8 text-lg">
        Robust IT support and device management for government, NGOs, and public sector organizations. Ensure operational continuity and data security with our specialized institutional services.
    </p>
    <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
        <!-- Device Management -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
           <Icon>
                <i slot="icon"> <SlidersIcon/> </i>
           </Icon>
            <h3 class="mb-2 text-xl font-bold">Device Management</h3>
            <p class="mb-4">
                Centralized monitoring and maintenance for all institutional devices.
            </p>
            <a
                href="#"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >Request Service</a
            >
        </div>

        <!-- Data Security -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
        <Icon>
            <i slot="icon"> <ShieldIcon/> </i>
       </Icon>
            <h3 class="mb-2 text-xl font-bold">Data Security</h3>
            <p class="mb-4">Protect sensitive information with advanced security solutions.</p>
            <a
                href="/Tasmal-X"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >See Features</a
            >
        </div>

        <!-- IT Consulting -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
        <Icon>
            <i slot="icon"> <BriefcaseIcon/> </i>
       </Icon>
            <h3 class="mb-2 text-xl font-bold">IT Consulting</h3>
            <p class="mb-4">Strategic guidance for digital transformation and compliance.</p>
            <a
                href="#"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >Learn More</a
            >
        </div>
    </div>
</section>