<script lang="ts">
  import { slide } from 'svelte/transition';
  
  interface FAQItem {
    question: string;
    answer: string;
  }

  const faqs: FAQItem[] = [
    { question: "What makes Calamos' protected ETFs different from structured notes?", answer: "Our ETFs use exchange-traded FLEX options instead of OTC derivatives, eliminating counterparty credit risk present in structured notes and annuities. This provides transparency, daily liquidity, and tax-efficient treatment with long-term capital gains." },
    { question: "How does 100% downside protection work?", answer: "Our Structured Protection ETFs use FLEX options to provide complete downside protection over one-year outcome periods. If the underlying index declines, your principal is protected. You participate in upside gains up to a cap, with tax-deferred growth during the outcome period." },
    { question: "Who is Calamos designed for?", answer: "We serve financial advisors at RIAs who need institutional-grade alternative solutions for their clients. Our products are ideal for investors seeking downside protection, especially those nearing or in retirement who can't afford significant portfolio losses." },
    { question: "What is the minimum investment?", answer: "Our ETFs trade like stocks with no minimum investment beyond the share price. Our Aksia partnership interval funds require just $2,500 minimum with no accreditation needed, democratizing access to institutional private markets." },
    { question: "How are Calamos ETFs tax-efficient?", answer: "FLEX options provide long-term capital gains treatment and tax-deferred growth during outcome periods. Unlike structured notes or annuities, our ETF structure offers transparent, exchange-traded vehicles with superior tax efficiency." },
    { question: "What is Calamos' track record?", answer: "Founded in 1977, we've pioneered alternative strategies for 48 years. We launched one of the first convertible mutual funds (1985), one of the first liquid alternative funds (1990), and the world's first 100% protected ETFs (2024). We manage $46B+ in AUM with $20B+ in alternatives." },
    { question: "How can financial advisors access Calamos products?", answer: "Our ETFs are available through major platforms including Schwab, Fidelity, TD Ameritrade, Morgan Stanley, and E*TRADE. We also work directly with RIAs through model portfolio platforms to help advisors overcome protection complexity." }
  ];

  let openIndex: number | null = null;

  function toggle(index: number) {
    openIndex = openIndex === index ? null : index;
  }
</script>

<section class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-4">
      <h2 class="font-serif text-4xl text-gray-900 mb-6">
        Frequently asked questions
      </h2>
      <a href="/" class="text-sm text-gray-900 border-b border-gray-300 pb-0.5 hover:border-black transition-colors">See all support</a>
    </div>
    
    <div class="lg:col-span-8">
      <div class="border-t border-gray-200">
        {#each faqs as faq, i}
          <div class="border-b border-gray-200">
            <button 
              class="w-full py-6 flex justify-between items-center text-left hover:bg-gray-50 transition-colors"
              on:click={() => toggle(i)}
            >
              <span class="text-lg text-gray-800">{faq.question}</span>
              <span class="text-2xl font-light text-gray-400 ml-4">
                {openIndex === i ? '−' : '+'}
              </span>
            </button>
            {#if openIndex === i}
              <div transition:slide class="pb-6 text-gray-500 leading-relaxed">
                {faq.answer}
              </div>
            {/if}
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
