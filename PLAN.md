O que é este projeto
DarkHole é uma agência criativa com site próprio. A plataforma tem estética dark futurista e serve como vitrine de portfólio e conversão de clientes. A experiência é imersiva: animações de scroll, glassmorphism e uma identidade visual pesada e coerente do início ao fim.

Como o projeto é organizado
src/
├── root.tsx               # Providers globais, tema e layout base
├── navigation/            # Rotas e configuração de menus
├── utils/                 # Helpers e constantes compartilhadas
└── pages/
    └── home/              # Página principal
        ├── home.tsx           # Composição da página
        ├── homeLayout.tsx     # Estrutura de grids e seções
        ├── components/        # Componentes locais da home
        └── hooks/             # Lógica de scroll e animação
Cada página vive dentro de src/pages/ com sua própria pasta. Componentes que pertencem só àquela página ficam em components/ dentro dela. Lógica de animação e scroll fica em hooks/. Nada global entra dentro de uma pasta de página.

Tema e identidade visual
O tema é dark futurista. Fundo escuro quase preto, superfícies sutilmente mais claras, texto claro e um único accent color em cyan.
TokenValorUsocolor.primary#06b6d4Cyan — botões, bordas ativas, glowcolor.bg#0a0a0fBackground principalcolor.surface#111118Cards, modais, painéiscolor.glassrgba(255,255,255,0.05)Glassmorphismcolor.text#e2e8f0Texto principalcolor.muted#64748bTexto secundário
Nunca use valores de cor hardcoded. Sempre referencie os tokens acima.

Como componentes funcionam

Hero Section — primeira impressão, efeito swirl, parallax vertical com Framer Motion
Project Cards — portfólio com mockups, glassmorphism + hover effects
CTA Section — encerramento da página, radial glow em cyan, foco em conversão

Animações usam useScroll e useTransform do Framer Motion. O visual reage diretamente ao scroll do usuário — não há animações soltas desconectadas da interação.

Regras que o modelo deve seguir

Componentes novos entram em pages/[pagina]/components/ — nunca na raiz
Cores sempre via tokens — nunca #06b6d4 direto no JSX ou CSS
Animações novas usam o padrão useScroll + useTransform já estabelecido
O estilo é sempre dark, denso, com glassmorphism onde há sobreposição de camadas
Sem elementos claros, sem fundos brancos, sem accent colors além do cyan