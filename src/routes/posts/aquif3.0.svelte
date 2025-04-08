<script context="module">
    export const metadata = {
        title: "The first research preview for aquif-3.0 is (finally) here",
        description: "our new AI model is a proof that size doesn't matter",
        date: "2025-03-03"
    };
</script>

<script>
    export const title = "The first research preview for aquif-3.0 is (finally) here";
    export const description = "our new AI model is a proof that size doesn't matter";
</script>

<div>
    <h1 class="text-3xl font-bold mb-6">The first research preview for aquif-3.0 is (finally) here</h1>
    <div class="prose prose-invert">
        <p>It's finally here!</p>
        <br>
        <p>aquif-3.0-preview-1 is not exactly a breakthrough, but our first step (hence the 1) at making size not matter for the intelligence of an AI. I could throw benchmarks at you (and that's what i'm going to do), but let's also see how using it actually feels like.</p>
        <br>
        <h2>Real Life usage</h2>
        <p>Ok, so here's the good, the bad and the ugly. This model is indeed GREAT at keeping stuff brief and simple to understand. Like, if i say it that i'm going through a rough time, it gives me a realistic, honest and personally great response for someone who feels that way.</p>
        <figure>
            <blockquote>
                <p>I'm really sorry that you're feeling this way, but I'm unable to provide the help that you need. It's really
                important to talk things over with someone who can, though, such as a mental health professional or a trusted
                person in your life.</p>
            </blockquote>
            <figcaption>
                aquif-3.0's first preview. Prompt: "i'm going through a rough time"
            </figcaption>
        </figure>
        <p>Compared to multi-trillion parameter models, such as GPT 4.5, it certainly isn't quite there. It's pretty impressive and honest, though, in terms of its capabilities. It knows well what it can and can't do, and that reduces hallucinations by a wide margin compared to models like aquif-2.2 and 2.1.</p>
        <br>
        <h2>Benchmaaaaaarks</h2>
        <p>Everyone loves benchmarks... It gives us a glimpse of what models are better at numerically, and aquif-3.0-preview-1 is almost there, that's awesome! In OCRBench, a benchmark for vision models (yep, we got a 2b vision model), preview-1 STOMPS Meta's Llama 3.2 <strong>11B</strong> vision model. That's crazy! Just look at the graph:</p>
        <figure>
            <img src="/assets/3.0-preview-1-vision.png" alt="aquif-3.0 benchmark comparison graph" class="w-full max-w-3xl mx-auto" />
            <figcaption class="text-center mt-2 text-sm text-gray-400">aquif-3.0-preview-1 vs Llama 3.2 11B and others on multiple benchmarks</figcaption>
        </figure>
        <br>
        <p>In terms of text itself, as vision is not all that makes a vision model, the situation is OK, to say the least. We are very close to  DeepSeek R1 Distill Qwen 7B on Alpaca-Eval-2, and consider this is our non-reasoning version with 70% less parameters than the chinese competitor.</p>
    </div>
    <a href="/blog" class="mt-8 inline-block text-primary hover:underline">← Back to Blog</a>
</div> 