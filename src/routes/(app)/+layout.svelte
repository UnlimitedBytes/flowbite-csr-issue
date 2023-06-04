<script>
    import { page } from '$app/stores';
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
    $: activeUrl = $page.url.pathname;
</script>

<Navbar let:hidden let:toggle>
    <NavBrand href="/">
        <img src="/images/logo.svg" class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" />
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"> Flowbite </span>
    </NavBrand>

    <NavHamburger on:click={toggle} />

    <NavUl {hidden}>
        <NavLi href="/" active={activeUrl == '/'}>Home</NavLi>
        <NavLi href="/about" active={activeUrl == '/about'}>About</NavLi>
    </NavUl>
</Navbar>

<slot />
