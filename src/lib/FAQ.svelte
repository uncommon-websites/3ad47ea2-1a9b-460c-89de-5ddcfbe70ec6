<script lang="ts">
  // FAQ component
  let openIndex: number | null = null;

  const faqs = [
    {
      question: "How does Prospera maintain self-custody?",
      answer: "Your assets never leave your wallet. Prospera's AI strategies execute through smart contracts that you control, ensuring you maintain complete custody while benefiting from sophisticated wealth management strategies."
    },
    {
      question: "What makes Prospera's AI different?",
      answer: "Our defensible AI risk engines are specifically trained on crypto market dynamics, using advanced machine learning to optimize leverage, rebalancing, and reserve management in real-time based on on-chain data and market conditions."
    },
    {
      question: "What assets does Prospera support?",
      answer: "Prospera focuses on premium crypto assets including BTC, ETH, and select high-quality tokens. We prioritize assets with deep liquidity and established track records to ensure optimal strategy execution."
    },
    {
      question: "How does leverage work on Prospera?",
      answer: "Our AI dynamically adjusts leverage positions based on market volatility, trend strength, and risk parameters. This intelligent approach maximizes compounding potential while managing downside risk more effectively than static leverage strategies."
    },
    {
      question: "Is Prospera suitable for beginners?",
      answer: "Prospera is designed for crypto-native investors who understand the risks of leverage and sophisticated trading strategies. We recommend having experience with DeFi and a solid understanding of crypto markets before using our platform."
    },
    {
      question: "How transparent are the strategies?",
      answer: "All strategies execute on-chain with complete transparency. You can verify every transaction, rebalancing decision, and leverage adjustment through blockchain explorers. Our AI's decision-making process is also auditable."
    },
    {
      question: "What are the fees?",
      answer: "Prospera charges a performance-based fee structure aligned with your success. We only earn when you earn, ensuring our incentives are completely aligned with maximizing your wealth growth."
    }
  ];

  function toggle(index: number) {
    openIndex = openIndex === index ? null : index;
  }
</script>

<section class="px-6 py-24 bg-gray-50">
  <div class="grid grid-cols-1 md:grid-cols-12 gap-8">
    <div class="md:col-span-4">
      <h2 class="text-3xl md:text-4xl font-normal text-gray-900 mb-6 max-w-xs leading-tight">
        Frequently asked questions
      </h2>
      <a href="/" class="text-sm text-gray-500 underline underline-offset-4 hover:text-black">See all support</a>
    </div>
    <div class="md:col-span-8">
      <div class="border-t border-gray-200">
        {#each faqs as faq, i}
          <div class="border-b border-gray-200">
            <button 
              class="w-full py-6 flex items-center justify-between text-left hover:bg-gray-100/50 transition-colors group"
              onclick={() => toggle(i)}
            >
              <span class="text-sm text-gray-700 group-hover:text-black">{faq.question}</span>
              <span class="text-gray-400 font-light text-xl ml-4">
                {openIndex === i ? '−' : '+'}
              </span>
            </button>
            {#if openIndex === i}
              <div class="pb-6 text-sm text-gray-500 leading-relaxed">
                {faq.answer}
              </div>
            {/if}
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
