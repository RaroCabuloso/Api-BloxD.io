Aqui está o guia organizado com emojis e formatação amigável para facilitar sua leitura e referência:

### 🧱 **Guia Completo da API Bloxd.io para Iniciantes** 🚀

---

### 🧩 **Introdução: Code Blocks e Code Boards**
- **Code Blocks**  
  - Aparecem no menu criativo  
  - Coloque no mundo → Clique/Pressione para executar  
  - ❗ Não precisa de "press to code" - roda imediatamente!

- **Code Boards**  
  - Texto **deve começar** com `press to code`  
  - ✏️ Dica: Adicione um espaço antes do texto para editar depois

---

### 🌐 **Variáveis Globais Úteis**
```javascript
api.log("👤 ID do jogador:", myId); 
api.log("📍 Posição do bloco:", thisPos);
```
- `myId`: ID do jogador atual  
- `thisPos`: Posição [x,y,z] do bloco/board  
- 📝 Use `api.log()` ou `console.log()` para depuração

---

### ⚙️ **Funções Principais do Objeto `api`**

#### 👥 **Jogadores & Entidades**
```javascript
// Exemplo: Vida do jogador
let vida = api.getHealth(myId);
api.setHealth(myId, 150); // 🩹 Aumenta vida para 150

// 💀 Killstreak
api.getCurrentKillstreak(myId);
api.clearKillstreak("player123");
```
- `getPosition()/setPosition()`  
- `getPlayerIds()` - Lista todos os IDs  
- `applyHealthChange()` - Dano/cura  
- `isAlive()` - Verifica se está vivo  

---

#### 💬 **Mensagens & Interface**
```javascript
// Mensagens personalizadas
api.sendMessage(myId, "🚨 Alerta!", { color: "red" });
api.broadcastMessage("🎉 Evento iniciado!", { color: "gold" });

// Mensagem flutuante
api.sendFlyingMiddleMessage(myId, ["⚠️","Cuidado!"], 80);

// Expulsar jogador
api.kickPlayer("player456", "Comportamento inadequado");
```

---

#### 🏃 **Movimentação & Física**
```javascript
// Fazer jogador pular
api.setVelocity(myId, 0, 9, 0); // 🚀 Salto alto

// Mudar pose do jogador
api.setPlayerPose(myId, "zombie"); // � Modo zumbi
```
- `applyImpulse()` - Aplica força  
- `spinKart()` - Gira kart  
- `getPlayerPhysicsState()` - Estado físico  

---

#### 🧱 **Blocos & Mundo**
```javascript
// Criar bloco de ouro
api.setBlock(0, 10, 0, "Block of Gold"); // ✨ Bloco precioso

// Preencher área com terra
api.setBlockRect([0,0,0], [5,5,5], "Dirt"); // ⬜ Cubo de terra
```
- `getBlock()` - Nome do bloco  
- `getBlockId()` - ID numérico (mais rápido)  
- `setBlockWalls()` - Só paredes  

---

#### 🎒 **Inventário & Itens**
```javascript
// Dar item ao jogador
api.giveItem(myId, "Diamond", 3); // 💎 3 diamantes!

// Verificar inventário
if(api.hasItem(myId, "Wood Plank")) {
  api.log("✅ Tem madeira!");
}
```
- `setItemSlot()` - Definir slot específico  
- `removeItemName()` - Remover itens  
- `inventoryIsFull()` - Verificar se cheio  

---

#### 👻 **Entidades & Customização**
```javascript
// Criar drop de item
api.createItemDrop(10, 20, 5, "Apple", 5); // 🍎 Maçãs no chão

// Skin de zumbi
api.changePlayerIntoSkin(myId, "body", "Zombie"); // 🧟‍♂️ Transformação!

// Jogador invisível
api.setPlayerOpacity(myId, 0); // 👻 Modo fantasma
```

---

#### ✨ **Efeitos & Som**
```javascript
// Aplicar efeito de velocidade
api.applyEffect(myId, "Speed", 10); // ⚡ Velocidade por 10s

// Partículas de bolhas
api.playParticleEffect({
  texture: "bubble",
  pos1: [0,0,0], 
  colorGradients: [{timeFraction:0, minColor:[0,0,255]}]
}); // 💧 Bolhas azuis

// Som de nível up
api.broadcastSound("levelup", 1.0); // 🔊 Efeito sonoro
```

---

### ⏰ **Callbacks de Eventos (Essenciais!)**
```javascript
// Quando jogador entra
onPlayerJoin = (playerId) => {
  api.sendMessage(playerId, "🫂 Bem-vindo ao nosso mundo!");
};

// A cada atualização do jogo
tick = (ms) => {
  // Lógica contínua aqui
};

// Quando jogador quebra bloco
onPlayerChangeBlock = (id, x, y, z) => {
  api.log(`⛏️ ${id} quebrou bloco em ${x},${y},${z}`);
};
```
📚 Lista completa em `CALLBACKS.md`

---

### ⚡ **Client Options (Superpoderes!)**
```javascript
// Habilidades especiais
api.setClientOption(myId, "speedMultiplier", 2.0); // 🏃💨 Velocidade 2x
api.setClientOption(myId, "airJumpCount", 2); // ✨ Salto duplo!
api.setClientOption(myId, "creative", true); // 🦅 Modo criativo (voar)
```
🔧 Opções em `CLIENT_OPTIONS.md`

---

### 👁️ **Entity Settings (Visuais)**
```javascript
// Jogador semi-transparente para você
api.setOtherEntitySetting(myId, "player123", "opacity", 0.5); // 👻 50% visível

// Mudar cor do nome
api.setOtherEntitySetting(myId, "player123", "nameColour", "purple"); // 🟣
```
🎨 Configurações em `ENTITY_SETTINGS.md`

---

### 🐷 **Mob Settings (Personalizar Criaturas)**
```javascript
// Porcos com 200 de vida
api.setDefaultMobSetting("Pig", "maxHealth", 200); // 🐖💪 Porcos fortões!

// Mob específico causa mais dano
api.setMobSetting(mobId123, "attackDamage", 15); // ⚔️ Ataque poderoso
```
📜 Referência em `MOB_SETTINGS.md`

---

### 🔚 **Conclusão**
- ✨ Dominou o básico da API Bloxd.io!  
- 💡 Use os arquivos de referência:
  - `PARTICLES.md` - Efeitos visuais  
  - `SOUND_NAMES.md` - Biblioteca de sons  
  - `README.md` - Documentação principal  
- 🚀 Crie mundos incríveis e compartilhe suas criações!

```javascript
// Exemplo final: Mensagem motivadora!
onPlayerJoin = (id) => {
  api.sendFlyingMiddleMessage(id, ["🌟","Você consegue!"], 100);
};
```
