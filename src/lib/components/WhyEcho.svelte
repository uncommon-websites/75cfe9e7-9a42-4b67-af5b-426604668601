<script>
  import SectionLabel from './SectionLabel.svelte';
</script>

<section class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-3">
      <SectionLabel label="Why Cal Uncommon" />
    </div>
    
    <div class="lg:col-span-9 grid grid-cols-1 md:grid-cols-2 gap-16">
      <div>
        <h2 class="font-serif text-3xl md:text-4xl leading-tight text-gray-900 mb-6">
          48 years of pioneering alternative strategies, now accessible to all investors
        </h2>
        <p class="text-gray-500 leading-relaxed">
          From convertible securities in 1977 to the world's first 100% protected ETFs, we bring institutional-grade innovation to individual investors through transparent, tax-efficient structures.
        </p>
      </div>
      
      <div class="flex gap-12 items-end pb-2">
        <div class="flex flex-col gap-1">
            <span class="text-4xl font-serif text-gray-900 mb-1">$46B+</span>
            <span class="text-xs text-gray-400">assets under management</span>
        </div>
        <div class="flex flex-col gap-1">
            <span class="text-4xl font-serif text-gray-900 mb-1">$20B+</span>
            <span class="text-xs text-gray-400">in alternative strategies</span>
        </div>
      </div>
    </div>
  </div>
</section>
