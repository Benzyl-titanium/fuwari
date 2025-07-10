<script>
import { onMount } from "svelte";
let enabled = true;
let isDark = false;

function updateDark() {
	isDark =
		typeof window !== "undefined" &&
		document.documentElement.classList.contains("dark");
}

onMount(() => {
	updateDark();
	const saved = localStorage.getItem("fireworks-enabled");
	if (saved === "true" || saved === "false") {
		enabled = saved === "true";
	} else {
		enabled = true;
		localStorage.setItem("fireworks-enabled", "true");
	}
	if (enabled) {
		loadFireworks();
	} else {
		removeFireworks();
	}
	const observer = new MutationObserver(updateDark);
	observer.observe(document.documentElement, {
		attributes: true,
		attributeFilter: ["class"],
	});
});

function toggle() {
	enabled = !enabled;
	localStorage.setItem("fireworks-enabled", enabled);
	if (enabled) {
		loadFireworks();
	} else {
		removeFireworks();
	}
}

function loadFireworks() {
	if (
		!window.__fireworks_inited &&
		!document.getElementById("__fireworks_script")
	) {
		const script = document.createElement("script");
		script.src = "/js/fireworks.js";
		script.id = "__fireworks_script";
		document.body.appendChild(script);
	}
}

function removeFireworks() {
	document.getElementById("__fireworks_canvas")?.remove();
	document.getElementById("__fireworks_pointer")?.remove();
	window.__fireworks_inited = false;
	document.getElementById("__fireworks_script")?.remove();
}
</script>

<button
  class="btn-plain scale-animation rounded-lg h-11 w-11 active:scale-90 group"
  aria-label="烟花开关"
  on:click={toggle}
  title="烟花开关"
>
  <span
    class={`text-[1.3rem] select-none transition-colors duration-200 translate-y-[1.5px]
      ${enabled
        ? 'text-[var(--primary)] group-hover:text-black/80 dark:group-hover:text-white/80'
        : (isDark
            ? 'text-white/80 group-hover:text-[var(--primary)]'
            : 'text-black/80 group-hover:text-[var(--primary)]')
    }`}
  >⌬</span>
</button> 