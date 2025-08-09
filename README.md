# Koch-Kompass
Entdecke täglich neue Rezepte, plane deine Mahlzeiten clever und erstelle blitzschnell deine persönliche Einkaufsliste – alles an einem Ort. So macht Kochen und Einkaufen Spaß und geht super einfach!
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>KochKompass – Rezept- & Einkaufslisten-App</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;700&display=swap');
  body {
    font-family: 'Nunito', sans-serif;
    margin: 0; padding: 0;
    background: #fff9f4;
    color: #3e3e3e;
    display: flex; flex-direction: column; min-height: 100vh;
  }
  header {
    background: #34a853;
    color: white;
    padding: 1.4rem 2rem;
    text-align: center;
    box-shadow: 0 3px 6px rgba(52,168,83,0.4);
  }
  header h1 {
    margin: 0;
    font-weight: 700;
    text-shadow: 0 2px 4px rgba(0,0,0,0.15);
  }
  main {
    flex: 1;
    padding: 1.5rem 2rem;
    max-width: 900px;
    margin: 0 auto 2rem auto;
  }
  h2 {
    color: #ea7600;
    text-shadow: 1px 1px 3px rgba(234,118,0,0.4);
  }
  h3 {
    color: #3a8dde;
    margin-top: 0;
  }
  button {
    background: #ea7600;
    color: white;
    border: none;
    padding: 0.6rem 1.3rem;
    border-radius: 25px;
    cursor: pointer;
    font-weight: 600;
    box-shadow: 0 3px 6px rgba(234,118,0,0.5);
    transition: background 0.3s ease;
  }
  button:hover {
    background: #cc6300;
    box-shadow: 0 4px 8px rgba(204,99,0,0.7);
  }
  input[type="search"] {
    padding: 0.6rem 1rem;
    width: 100%;
    margin-bottom: 1.4rem;
    border-radius: 30px;
    border: 2px solid #34a853;
    font-size: 1.05rem;
    transition: border-color 0.3s ease;
  }
  input[type="search"]:focus {
    border-color: #ea7600;
    outline: none;
  }
  .recipe-list {
    max-height: 360px;
    overflow-y: auto;
    border: 2px solid #3a8dde;
    border-radius: 15px;
    padding: 0.8rem;
    background: white;
    box-shadow: 0 4px 10px rgba(58,141,222,0.1);
  }
  .recipe-item {
    padding: 0.7rem 1rem;
    border-bottom: 1px solid #eee;
    cursor: pointer;
    font-weight: 600;
    color: #3e3e3e;
    border-radius: 12px;
    transition: background 0.25s ease;
  }
  .recipe-item:hover {
    background: #eaeaea;
  }
  .recipe-detail {
    margin-top: 1.8rem;
    background: white;
    padding: 1.5rem 1.7rem;
    border-radius: 20px;
    box-shadow: 0 0 14px rgba(58,141,222,0.25);
  }
  .ingredients-list {
    list-style: none;
    padding-left: 0;
    font-size: 1.05rem;
    color: #555;
  }
  .ingredients-list li {
    margin: 0.35rem 0;
  }
  .shopping-list {
    margin-top: 2.5rem;
    background: white;
    padding: 1.5rem 1.8rem;
    border-radius: 20px;
    box-shadow: 0 0 14px rgba(234,118,0,0.35);
  }
  .shopping-list h2 {
    margin-top: 0;
    color: #ea7600;
  }
  .shopping-item {
    display: flex;
    align-items: center;
    margin-bottom: 0.4rem;
    font-size: 1.05rem;
    color: #444;
  }
  .shopping-item input[type="checkbox"] {
    margin-right: 0.6rem;
    transform: scale(1.25);
    cursor: pointer;
  }
  img.recipe-image {
    max-width: 100%;
    border-radius: 20px;
    margin-bottom: 1rem;
    box-shadow: 0 6px 12px rgba(58,141,222,0.2);
  }
  #new-random-recipe-btn {
    margin-top: 0.8rem;
    box-shadow: 0 5px 12px rgba(58,141,222,0.5);
  }
  #close-detail-btn {
    margin-left: 1rem;
    background: #999;
    box-shadow: none;
  }
  @media (max-width: 600px) {
    main {
      padding: 1rem;
    }
  }
</style>
</head>
<body>

<header>
  <h1>KochKompass</h1>
</header>

<main>
  <section id="random-recipe-section">
    <h2>Rezept des Tages</h2>
    <div id="random-recipe-container"></div>
    <button id="new-random-recipe-btn">Neues Rezept anzeigen</button>
  </section>

  <section id="all-recipes-section" style="margin-top: 2rem;">
    <h2>Alle Rezepte</h2>
    <input type="search" id="search-input" placeholder="Rezepte suchen..." autocomplete="off" />
    <div class="recipe-list" id="recipe-list" role="list"></div>
  </section>

  <section id="recipe-detail-section" style="display:none;">
    <h2 id="recipe-detail-name"></h2>
    <img id="recipe-detail-image" class="recipe-image" alt="Rezeptbild" />
    <p id="recipe-detail-description"></p>
    <h3>Zutaten</h3>
    <ul class="ingredients-list" id="ingredients-list"></ul>
    <button id="add-to-shopping-list-btn">Zur Einkaufsliste hinzufügen</button>
    <button id="close-detail-btn">Schließen</button>
  </section>

  <section class="shopping-list" id="shopping-list-section">
    <h2>Einkaufsliste</h2>
    <div id="shopping-list" role="list"></div>
    <button id="clear-shopping-list-btn" style="margin-top:1rem; background:#e74c3c;">Einkaufsliste löschen</button>
  </section>
</main>

<script>
  const recipes = [
    { name: "Spaghetti Bolognese", description: "Klassische italienische Pasta mit Hackfleischsoße.", ingredients: ["Spaghetti", "Hackfleisch", "Tomatensoße", "Zwiebel", "Knoblauch"], image: "https://via.placeholder.com/600x400?text=Spaghetti+Bolognese" },
    { name: "Chicken Curry", description: "Würziges Curry mit Hähnchen und Reis.", ingredients: ["Hähnchenbrust", "Currypaste", "Kokosmilch", "Reis", "Paprika"], image: "https://via.placeholder.com/600x400?text=Chicken+Curry" },
    { name: "Caesar Salad", description: "Frischer Salat mit Caesar-Dressing und Croutons.", ingredients: ["Römersalat", "Croutons", "Parmesan", "Caesar-Dressing"], image: "https://via.placeholder.com/600x400?text=Caesar+Salad" },
    // ... (jetzt 47 weitere Rezepte folgen)
  ];

  for(let i=4; i<=50; i++) {
    recipes.push({
      name: `Rezept Nr. ${i}`,
      description: `Beschreibung für Rezept Nr. ${i}.`,
      ingredients: [`Zutat A${i}`, `Zutat B${i}`, `Zutat C${i}`],
      image: `https://via.placeholder.com/600x400?text=Rezept+Nr+${i}`
    });
  }

  const randomRecipeContainer = document.getElementById("random-recipe-container");
  const newRandomRecipeBtn = document.getElementById("new-random-recipe-btn");
  const recipeListDiv = document.getElementById("recipe-list");
  const searchInput = document.getElementById("search-input");
  const recipeDetailSection = document.getElementById("recipe-detail-section");
  const recipeDetailName = document.getElementById("recipe-detail-name");
  const recipeDetailImage = document.getElementById("recipe-detail-image");
  const recipeDetailDescription = document.getElementById("recipe-detail-description");
  const ingredientsList = document.getElementById("ingredients-list");
  const addToShoppingListBtn = document.getElementById("add-to-shopping-list-btn");
  const closeDetailBtn = document.getElementById("close-detail-btn");
  const shoppingListDiv = document.getElementById("shopping-list");
  const clearShoppingListBtn = document.getElementById("clear-shopping-list-btn");

  let currentRecipe = null;
  let shoppingList = JSON.parse(localStorage.getItem("shoppingList") || "[]");

  function displayRecipe(recipe, container, clickable = true) {
    container.innerHTML = `
      <h3>${recipe.name}</h3>
      <img src="${recipe.image}" alt="${recipe.name}" style="max-width:100%; border-radius:20px; margin-bottom:0.5rem;">
      <p>${recipe.description}</p>
      <strong>Zutaten:</strong> ${recipe.ingredients.join(", ")}
    `;
    if(clickable) {
      container.style.cursor = "pointer";
      container.onclick = () => openRecipeDetail(recipe);
    } else {
      container.style.cursor = "default";
      container.onclick = null;
    }
  }

  function openRecipeDetail(recipe) {
    currentRecipe = recipe;
    recipeDetailName.textContent = recipe.name;
    recipeDetailImage.src = recipe.image;
    recipeDetailDescription.textContent = recipe.description;
    ingredientsList.innerHTML = "";
    recipe.ingredients.forEach(ing => {
      const li = document.createElement("li");
      li.textContent = ing;
      ingredientsList.appendChild(li);
    });
    recipeDetailSection.style.display = "block";
    window.scrollTo({top:0, behavior:"smooth"});
  }

  function closeRecipeDetail() {
    recipeDetailSection.style.display = "none";
  }

  function addIngredientsToShoppingList() {
    currentRecipe.ingredients.forEach(ing => {
      if(!shoppingList.includes(ing)) {
        shoppingList.push(ing);
      }
    });
    saveShoppingList();
    renderShoppingList();
    alert("Zutaten wurden zur Einkaufsliste hinzugefügt.");
  }

  function renderRecipeList(filter = "") {
    recipeListDiv.innerHTML = "";
    const filtered = recipes.filter(r => 
      r.name.toLowerCase().includes(filter.toLowerCase()) ||
      r.description.toLowerCase().includes(filter.toLowerCase())
    );
    filtered.forEach(recipe => {
      const div = document.createElement("div");
      div.className = "recipe-item";
      div.textContent = recipe.name;
      div.onclick = () => openRecipeDetail(recipe);
      recipeListDiv.appendChild(div);
    });
  }

  function renderShoppingList() {
    shoppingListDiv.innerHTML = "";
    shoppingList.forEach((item, idx) => {
      const div = document.createElement("div");
      div.className = "shopping-item";

      const checkbox = document.createElement("input");
      checkbox.type = "checkbox";
      checkbox.id = `chk-${idx}`;
      checkbox.checked = false;
      checkbox.onchange = () => {
        if(checkbox.checked) {
          shoppingList.splice(idx,1);
          saveShoppingList();
          renderShoppingList();
        }
      };

      const label = document.createElement("label");
      label.htmlFor = `chk-${idx}`;
      label.textContent = item;

      div.appendChild(checkbox);
      div.appendChild(label);
      shoppingListDiv.appendChild(div);
    });
  }

  function saveShoppingList() {
    localStorage.setItem("shoppingList", JSON.stringify(shoppingList));
  }

  function showRandomRecipe() {
    const idx = Math.floor(Math.random() * recipes.length);
    displayRecipe(recipes[idx], randomRecipeContainer, false);
  }

  // Events
  newRandomRecipeBtn.onclick = showRandomRecipe;
  addToShoppingListBtn.onclick = addIngredientsToShoppingList;
  closeDetailBtn.onclick = closeRecipeDetail;
  searchInput.oninput = () => renderRecipeList(searchInput.value);
  clearShoppingListBtn.onclick = () => {
    if(confirm("Einkaufsliste wirklich löschen?")) {
      shoppingList = [];
      saveShoppingList();
      renderShoppingList();
    }
  };

  // Init
  renderRecipeList();
  renderShoppingList();
  showRandomRecipe();
</script>

</body>
</html>
