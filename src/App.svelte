<script>
    import "./app.css";
    import { Button } from "$lib/components/ui/button";
    import { Sun, Moon, Monitor } from 'lucide-svelte';
    import { Router, Link, Route } from "svelte-routing";
    import Blog from './routes/Blog.svelte';
    import BlogPost from './routes/BlogPost.svelte';
    let theme = 'system';

    let currentPath = window.location.hash.slice(1) || '/';
    if (sessionStorage.redirect) {
        currentPath = sessionStorage.redirect;
        sessionStorage.removeItem('redirect');
    }

    function handleHashChange() {
        currentPath = window.location.hash.slice(1) || '/';
    }

    window.addEventListener('hashchange', handleHashChange);

    function applyTheme() {
        document.documentElement.classList.remove('light', 'dark');
        if (theme === 'system') {
            const systemTheme = window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light';
            document.documentElement.classList.add(systemTheme);
        } else {
            document.documentElement.classList.add(theme);
        }
    }

    function toggleTheme() {
        theme = theme === 'light' ? 'dark' : theme === 'dark' ? 'system' : 'light';
        applyTheme();
    }

    applyTheme();
</script>

<Router url={currentPath}>
    <div class="flex flex-col min-h-screen bg-background">
        <header class="p-4 border-b">
            <div class="container flex items-center justify-between">
                <Link to="/" class="text-2xl font-bold">aquif Research</Link>
                <Button on:click={toggleTheme} variant="ghost" size="icon">
                    {#if theme === 'light'}
                        <Sun class="h-4 w-4" />
                    {:else if theme === 'dark'}
                        <Moon class="h-4 w-4" />
                    {:else}
                        <Monitor class="h-4 w-4" />
                    {/if}
                </Button>
            </div>
        </header>

        <main class="flex-grow container py-8">
            <Route path="/">
                <div class="flex flex-col items-center justify-center min-h-[calc(100vh-200px)]">
                    <h1 class="text-3xl font-bold mb-4">"aquif-3.0 is very good"</h1>
                    <p class="text-lg mb-8">- 𝕮𝖗𝖔𝖎𝖘𝖘𝖆𝖓𝖙, 2025</p>
                    <a href="/blog" class="inline-block px-6 py-2 bg-primary text-primary-foreground rounded-lg hover:bg-primary/90 transition-colors">
                        aquif-3.0-preview-1 is on the blog
                    </a>
                </div>
            </Route>
            <Route path="/blog/:slug" let:params>
                <BlogPost {params} />
            </Route>
            <Route path="/blog">
                <Blog />
            </Route>
        </main>

        <footer class="text-center p-4 text-sm text-muted-foreground border-t">
            made by <a href="https://aquiffoo.vercel.app" class="hover:underline">aquiffoo</a>
        </footer>
    </div>
</Router>

<style>
    .logo {
        height: 6em;
        padding: 1.5em;
        will-change: filter;
        transition: filter 300ms;
    }
    .logo:hover {
        filter: drop-shadow(0 0 2em #646cffaa);
    }
    .logo.svelte:hover {
        filter: drop-shadow(0 0 2em #ff3e00aa);
    }
    .read-the-docs {
        color: #888;
    }
</style>
