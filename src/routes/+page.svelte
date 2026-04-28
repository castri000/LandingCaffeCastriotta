<script lang="ts">
  import TopBar from '$lib/components/TopBar.svelte';
  import Header from '$lib/components/Header.svelte';
  import TextImageSection from '$lib/components/TextImageSection.svelte';
  import QuoteSection from '$lib/components/QuoteSection.svelte';
  import InfiniteCarousel from '$lib/components/InfiniteCarousel.svelte';
  import CardsGrid from '$lib/components/CardsGrid.svelte';
  import ImgChange from '$lib/components/ImgChange.svelte';

  // Asset URLs from Figma
  const imgImgDefault = "https://www.figma.com/api/mcp/asset/7f14ac3c-ffb3-4324-b159-054c255d1676";
  const imgImgHover = "https://www.figma.com/api/mcp/asset/1228e4d2-71db-4dc1-9c9a-faef697257cd";
  const imgCoffeeIcon1 = "https://www.figma.com/api/mcp/asset/a747f0da-dac1-4c04-940d-46d04addb7fa";
  const imgCoffeeIcon2 = "https://www.figma.com/api/mcp/asset/e7898733-b9aa-44fb-87b0-3e709a43e463";
  const imgCoffeeIcon3 = "https://www.figma.com/api/mcp/asset/758cd93f-3c13-4d7f-b141-7e51bc415b4d";
  const imgCoffeeIcon4 = "https://www.figma.com/api/mcp/asset/ce26d7bf-5a03-4fa3-af5c-0d663684449a";

  const productCards = [
    {
      title: 'Caffe',
      subtitle: 'ESPRESSO',
      description: "L'espresso è l'essenza del caffè italiano: intenso, concentrato, immediato. In pochi secondi sprigiona aromi profondi e una crema dorata che racconta tutta la sua forza. Il gesto quotidiano che risveglia, accompagna e mette in pausa.",
      imageUrl: imgCoffeeIcon4,
      side: "left"
    },
    {
      title: 'Caffe',
      subtitle: 'CAPPUCCINO',
      description: 'Il cappuccino è equilibrio: l\'abbraccio tra espresso e latte montato che crea una morbidezza unica. Cremoso, rotondo, avvolgente, è il simbolo delle mattine italiane e del piacere lento di un inizio giornata fatto bene.',
      imageUrl: imgCoffeeIcon3,
      side: "right"
    },
    {
      title: 'Caffe',
      subtitle: 'ICE LATTE',
      description: 'Fresco, leggero e vellutato, l\'ice latte unisce espresso e latte freddo con ghiaccio. La versione estiva del comfort: rinfrescante e con carattere, perfetto per chi vuole gusto e freschezza in un solo sorso.',
      imageUrl: imgCoffeeIcon2,
      side: "left"
    },
    {
      title: 'Caffe',
      subtitle: 'CREMA',
      description: 'La crema caffè è un piccolo dessert in tazza: soffice, fredda e irresistibile. Un mix di espresso e panna montata che diventa una mousse leggera, ideale quando vuoi qualcosa di dolce senza esagerare.',
      imageUrl: imgCoffeeIcon1,
      side: "right"
    }
  ];
</script>

<div class="page-container">
  <TopBar />
  <Header title="titolo" videoUrl="/video/video caffe 3.mp4"/>
  
  <TextImageSection
    heading="L'ARTE DEL CAFFÈ"
    subheading="Un rituale quotidiano"
    description="Il caffè è un gesto semplice che racchiude un mondo intero. Dal profumo che si diffonde appena versato, al calore che avvolge le mani, ogni tazza diventa un piccolo momento di pausa, un invito a respirare e rallentare. È un compagno silenzioso che accompagna conversazioni, idee, ricordi e nuovi inizi. Che sia intenso, morbido o aromatico, il caffè trasforma l'ordinario in un rituale quotidiano, capace di regalare un attimo di autentico benessere."
  >
    <ImgChange
      defaultImageUrl={imgImgDefault}
      hoverImageUrl={imgImgHover}
      alt="L'arte del caffè"
    />
  </TextImageSection>

  <QuoteSection quote='"Scopri il gusto, la cura e la passione che mettiamo in ogni miscela: un percorso fatto di aromi, qualità e piccoli momenti da condividere."' />

  <CardsGrid cards={productCards} />

  <InfiniteCarousel />
</div>

<style>
  .page-container {
    background-color: var(--color-background-primary);
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
</style>
