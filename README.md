# Criando um mapa conceitual com estrutura visual semelhante ao mapa mental, mas com foco nas relações entre conceitos.
mapa_conceitual = Digraph('Mapa Conceitual', format='png')
mapa_conceitual.attr(rankdir='LR', size='12')

# Estilo geral dos nós.
mapa_conceitual.attr('node', shape='box', style='rounded, filled', color='lightyellow', fontname='Arial')

# Nó principal
mapa_conceitual.node('MM', 'Matemática Instrumental')

# Tópicos principais
mapa_conceitual.node('Intro', 'Introdução à Matemática Instrumental')
mapa_conceitual.node('Conj', 'Fundamentos de Sistemas de Conjuntos')
mapa_conceitual.node('Alg', 'Ferramentas de Álgebra')
mapa_conceitual.node('Trig', 'Noções de Trigonometria')
mapa_conceitual.node('Raz', 'Estudo de Razão e Proporção')
mapa_conceitual.node('Matr', 'Aplicações de Matrizes e Sistemas Lineares')
mapa_conceitual.node('Simb', 'Simbologias e Aplicações Numéricas')
mapa_conceitual.node('Des', 'Desafios no Cotidiano')

# Conexões principais com o nó central
for node in ['Intro', 'Conj', 'Alg', 'Trig', 'Raz', 'Matr', 'Simb', 'Des']:
    mapa_conceitual.edge('MM', node)

# Relações entre os conceitos
mapa_conceitual.edge('Conj', 'Alg', label='Álgebra usa conceitos de conjuntos', color='grey')
mapa_conceitual.edge('Alg', 'Matr', label='Base para matrizes', color='grey')
mapa_conceitual.edge('Raz', 'Trig', label='Proporções em triângulos', color='grey')
mapa_conceitual.edge('Trig', 'Matr', label='Aplicações avançadas', color='grey')
mapa_conceitual.edge('Simb', 'Des', label='Aplicações práticas', color='grey')
mapa_conceitual.edge('Raz', 'Simb', label='Razões numéricas', color='grey')

# Renderizando o mapa conceitual.
output_path_concept = "/mnt/data/Mapa_Conceitual_Matematica"
mapa_conceitual.render(output_path_concept, view=False)

output_path_concept + ".png"

