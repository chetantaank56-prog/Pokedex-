# Pokedex-
Pokedex for pokebedrock 
<style>
  /* Added Type-specific colors and hover effects */
  .card { 
    background: #2d2d2d; 
    padding: 15px; 
    border-radius: 12px; 
    border-left: 5px solid #ff1c1c; 
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .card:hover { 
    transform: translateY(-5px); 
    box-shadow: 0 5px 15px rgba(0,0,0,0.3); 
  }
  
  /* Color mapping for types */
  .type-dark { background: #705746; }
  .type-dragon { background: #6F35FC; }
  .type-water { background: #6390F0; }
  .type-psychic { background: #F95587; }
</style>

<script>
  // Updated render function to include dynamic CSS classes
  function render(list) {
    const container = document.getElementById('dex-grid');
    container.innerHTML = list.map(p => {
      const mainType = p.type.split('/')[0].toLowerCase();
      return `
        <div class="card">
          <h3>${p.name}</h3>
          <div class="type type-${mainType}">${p.type}</div>
          <p>📍 ${p.biome}</p>
          <p class="rarity">✨ ${p.rarity}</p>
        </div>
      `;
    }).join('');
  }
</script>
const pokedexData = [
  { id: 1, name: "Absol", type: "Dark", biome: "Mountain Peaks", rarity: "Rare", is3D: true },
  { id: 2, name: "Zekrom", type: "Dragon/Electric", biome: "Unknown (Event)", rarity: "Legendary", is3D: true },
  { id: 3, name: "Lechonk", type: "Normal", biome: "Plains", rarity: "Common", is3D: true },
  // Add more from the PokeBedrock GitHub/Discord
];
