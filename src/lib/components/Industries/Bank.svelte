<script>
	import { LockIcon, ShieldIcon, ToolIcon } from "svelte-feather-icons";
	import Icon from "../icon.svelte";

</script>
<!-- Banks Section -->
<section id="banks" class="mb-10 bg-purple-200 p-2 rounded-lg">
    <h2 class="mb-2 text-2xl font-bold">Banks</h2>
    <p class="mb-8 text-lg">
        Secure, compliant cheque encoding and device repair for financial institutions. Minimize
        downtime, ensure regulatory compliance, and protect sensitive data with our trusted solutions.
    </p>
    <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
        <!-- Hardware Support -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
           <Icon>
                <i slot="icon"> <ToolIcon/> </i>
           </Icon>
            <h3 class="mb-2 text-xl font-bold">Hardware Support</h3>
            <p class="mb-4">
                Expert maintenance and rapid repair for printers, photocopiers and more.
            </p>
            <a
                href="#"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >Request Service</a
            >
        </div>

        <!-- Tasmal x Software -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
        <Icon>
            <i slot="icon"> <ShieldIcon/> </i>
       </Icon>
            <h3 class="mb-2 text-xl font-bold">Tasmal x Software</h3>
            <p class="mb-4">Industry-leading cheque encoding with advanced security and compliance.</p>
            <a
                href="/Tasmal-X"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >See Features</a
            >
        </div>

        <!-- Data Security -->
        <div
            class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
        >
        <Icon>
            <i slot="icon"> <LockIcon/> </i>
       </Icon>
            <h3 class="mb-2 text-xl font-bold">Data Security</h3>
            <p class="mb-4">Strict protocols to safeguard sensitive banking information.</p>
            <a
                href="#"
                class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
                >Learn More</a
            >
        </div>
    </div>
</section>