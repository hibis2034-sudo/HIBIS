import productImage from 'figma:asset/b86ae6795acb64d9c9f8f98cd6539aa85ab6b04b.png';

interface HeroProps {
  language: 'en' | 'fr';
}

const translations = {
  en: {
    welcome: 'Welcome to HIBIS',
    subtitle: 'Premium Hibiscus Wine',
    description: 'Experience the exquisite taste of our handcrafted hibiscus wine. Made with passion and tradition.',
    cta: 'Discover Our Collection',
  },
  fr: {
    welcome: 'Bienvenue chez HIBIS',
    subtitle: 'Vin d\'Hibiscus Premium',
    description: 'Découvrez le goût exquis de notre vin d\'hibiscus artisanal. Fabriqué avec passion et tradition.',
    cta: 'Découvrez Notre Collection',
  },
};

export function Hero({ language }: HeroProps) {
  const t = translations[language];

  const scrollToWine = () => {
    const element = document.getElementById('wine');
    element?.scrollIntoView({ behavior: 'smooth' });
  };

  return (
    <section id="home" className="relative min-h-[600px] flex items-center justify-center bg-gradient-to-br from-[#800020] via-[#600018] to-[#400010]">
      <div className="absolute inset-0 opacity-20">
        <img
          src="https://images.unsplash.com/photo-1699712280943-7db4f5f03e3e?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHx3aW5lJTIwdmluZXlhcmQlMjBidXJndW5keXxlbnwxfHx8fDE3NjI0Mjc4MDJ8MA&ixlib=rb-4.1.0&q=80&w=1080&utm_source=figma&utm_medium=referral"
          alt="Background"
          className="w-full h-full object-cover"
        />
      </div>
      <div className="container mx-auto px-4 py-20 relative z-10">
        <div className="grid md:grid-cols-2 gap-12 items-center">
          <div className="text-white">
            <h1 className="text-[#D4AF37] mb-4">{t.welcome}</h1>
            <p className="text-white/90 mb-8 max-w-lg">
              {t.description}
            </p>
            <button
              onClick={scrollToWine}
              className="bg-[#D4AF37] text-[#800020] px-8 py-3 rounded-lg hover:bg-[#C4A037] transition-all transform hover:scale-105 shadow-lg"
            >
              {t.cta}
            </button>
          </div>
          <div className="flex justify-center">
            <img
              src={productImage}
              alt="HIBIS Wine Bottle"
              className="max-w-sm w-full rounded-lg shadow-2xl"
            />
          </div>
        </div>
      </div>
    </section>
  );
}
