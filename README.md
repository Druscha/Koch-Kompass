# Koch-Kompass
Entdecke täglich neue Rezepte, plane deine Mahlzeiten clever und erstelle blitzschnell deine persönliche Einkaufsliste – alles an einem Ort. So macht Kochen und Einkaufen Spaß und geht super einfach!
import { useState, useEffect } from "react";

const recipes = [
  {
    name: "Spaghetti Bolognese",
    description: "Klassische italienische Pasta mit würziger Hackfleischsoße.",
    ingredients: [
      "200 g Spaghetti",
      "150 g Rinderhackfleisch",
      "1 kleine Zwiebel, fein gehackt",
      "1 Knoblauchzehe, gepresst",
      "200 ml passierte Tomaten",
      "2 EL Olivenöl",
      "Salz und Pfeffer nach Geschmack",
      "1 TL getrockneter Oregano",
      "Parmesan zum Servieren"
    ]
  },
  {
    name: "Chicken Curry",
    description: "Würziges Curry mit zartem Hähnchenfleisch und Kokosmilch.",
    ingredients: [
      "300 g Hähnchenbrust, gewürfelt",
      "1 Zwiebel, gewürfelt",
      "2 EL Currypaste (rot oder gelb)",
      "200 ml Kokosmilch",
      "1 rote Paprika, in Streifen",
      "150 g Basmatireis",
      "2 EL Pflanzenöl",
      "Salz nach Geschmack"
    ]
  },
  {
    name: "Vegetarisches Chili",
    description: "Würziges Chili mit Bohnen, Mais und Gemüse.",
    ingredients: [
      "1 Dose Kidneybohnen (ca. 400 g), abgetropft",
      "1 Dose Mais (ca. 300 g), abgetropft",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "1 Dose gehackte Tomaten (400 g)",
      "150 g Reis",
      "2 EL Öl",
      "Salz, Pfeffer, Chili"
    ]
  },
  {
    name: "Caesar Salad",
    description: "Frischer Salat mit Hähnchen, Croutons und Caesar-Dressing.",
    ingredients: [
      "1 Kopf Römersalat",
      "200 g gegrillte Hähnchenbrust, in Streifen",
      "50 g Parmesan, gehobelt",
      "100 g Croutons",
      "4 EL Caesar-Dressing"
    ]
  },
  {
    name: "Pancakes",
    description: "Fluffige Frühstücks-Pancakes mit Ahornsirup.",
    ingredients: [
      "200 g Mehl",
      "300 ml Milch",
      "2 Eier",
      "1 EL Zucker",
      "1 TL Backpulver",
      "Butter zum Braten",
      "Ahornsirup zum Servieren"
    ]
  },
  {
    name: "Tomatensuppe",
    description: "Cremige Suppe aus frischen Tomaten und Basilikum.",
    ingredients: [
      "1 kg reife Tomaten",
      "1 Zwiebel",
      "2 Knoblauchzehen",
      "500 ml Gemüsebrühe",
      "2 EL Olivenöl",
      "Salz, Pfeffer",
      "Frisches Basilikum"
    ]
  },
  {
    name: "Lasagne",
    description: "Schichtweise gebackene Nudelauflauf mit Fleisch und Käse.",
    ingredients: [
      "12 Lasagneblätter",
      "400 g Hackfleisch",
      "1 Zwiebel",
      "2 Knoblauchzehen",
      "500 ml passierte Tomaten",
      "250 g Ricotta",
      "200 g geriebener Mozzarella",
      "2 EL Olivenöl",
      "Salz, Pfeffer, italienische Kräuter"
    ]
  },
  {
    name: "Quiche Lorraine",
    description: "Herzhafte Quiche mit Speck und Käse.",
    ingredients: [
      "1 Mürbeteigboden",
      "150 g Speckwürfel",
      "3 Eier",
      "200 ml Sahne",
      "150 g geriebener Käse",
      "Salz, Pfeffer, Muskatnuss"
    ]
  },
  {
    name: "Gemüsepfanne",
    description: "Bunte Pfanne mit frischem Gemüse und Sojasoße.",
    ingredients: [
      "1 Brokkoli",
      "1 Paprika",
      "2 Karotten",
      "100 g Champignons",
      "2 EL Sojasoße",
      "1 EL Sesamöl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Schnitzel mit Kartoffelsalat",
    description: "Klassisches Wiener Schnitzel mit Kartoffelsalat.",
    ingredients: [
      "2 Schweineschnitzel (je ca. 150 g)",
      "2 Eier",
      "100 g Mehl",
      "150 g Semmelbrösel",
      "4 große Kartoffeln",
      "2 EL Essig",
      "2 EL Öl",
      "1 kleine Zwiebel, gehackt",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Pilzrisotto",
    description: "Cremiges Risotto mit frischen Pilzen.",
    ingredients: [
      "200 g Risottoreis",
      "300 g Champignons, in Scheiben",
      "1 Zwiebel, gehackt",
      "750 ml Gemüsebrühe",
      "100 ml Weißwein",
      "50 g Parmesan",
      "2 EL Butter",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Hummus",
    description: "Cremiger Kichererbsenaufstrich mit Tahini.",
    ingredients: [
      "250 g Kichererbsen (vorgekocht oder aus der Dose)",
      "2 EL Tahini (Sesampaste)",
      "2 EL Olivenöl",
      "Saft einer Zitrone",
      "1 Knoblauchzehe",
      "Salz, Kreuzkümmel"
    ]
  },
  {
    name: "Griechischer Salat",
    description: "Frischer Salat mit Feta, Oliven und Gemüse.",
    ingredients: [
      "2 Tomaten, gewürfelt",
      "1 Gurke, gewürfelt",
      "1 rote Zwiebel, in Ringe",
      "100 g Feta",
      "50 g schwarze Oliven",
      "3 EL Olivenöl",
      "1 EL Oregano",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Bananenbrot",
    description: "Saftiges Brot mit reifen Bananen.",
    ingredients: [
      "3 reife Bananen",
      "200 g Mehl",
      "150 g Zucker",
      "2 Eier",
      "100 ml Öl",
      "1 TL Backpulver",
      "1 Prise Salz"
    ]
  },
  {
    name: "Hähnchen-Satay",
    description: "Gegrillte Hähnchenspieße mit Erdnusssauce.",
    ingredients: [
      "300 g Hähnchenbrust, in Streifen",
      "2 EL Sojasoße",
      "1 EL Limettensaft",
      "Spieße aus Holz",
      "Erdnusssauce (Erdnussbutter, Kokosmilch, Sojasoße, Limette)"
    ]
  },
  {
    name: "Couscous-Salat",
    description: "Frischer Salat mit Couscous, Gemüse und Kräutern.",
    ingredients: [
      "150 g Couscous",
      "200 ml Gemüsebrühe",
      "1 Paprika, gewürfelt",
      "1 Gurke, gewürfelt",
      "1 Bund Petersilie, gehackt",
      "3 EL Olivenöl",
      "Saft einer Zitrone",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Lachsfilet mit Spargel",
    description: "Gegrilltes Lachsfilet mit grünem Spargel.",
    ingredients: [
      "2 Lachsfilets (je ca. 150 g)",
      "500 g grüner Spargel",
      "2 EL Olivenöl",
      "Salz und Pfeffer",
      "Zitrone zum Servieren"
    ]
  },
  {
    name: "Schoko-Muffins",
    description: "Saftige Muffins mit Schokoladenstückchen.",
    ingredients: [
      "200 g Mehl",
      "50 g Kakaopulver",
      "150 g Zucker",
      "2 Eier",
      "100 ml Milch",
      "100 g Butter",
      "100 g Schokostückchen",
      "1 TL Backpulver"
    ]
  },
  {
    name: "Tacos mit Hackfleisch",
    description: "Knusprige Tacos gefüllt mit würzigem Hackfleisch und Gemüse.",
    ingredients: [
      "200 g Rinderhackfleisch",
      "1 Zwiebel, gehackt",
      "1 Dose Mais (ca. 300 g), abgetropft",
      "1 Paprika, gewürfelt",
      "Taco-Schalen",
      "Salat, Tomaten, Käse, Salsa"
    ]
  },
  {
    name: "Gemüseomelett",
    description: "Fluffiges Omelett mit Gemüsefüllung.",
    ingredients: [
      "3 Eier",
      "50 ml Milch",
      "1 kleine Zucchini, gewürfelt",
      "1 Tomate, gewürfelt",
      "Salz und Pfeffer",
      "1 EL Butter"
    ]
  },
  {
    name: "Pizzateig Grundrezept",
    description: "Grundrezept für knusprigen Pizzateig.",
    ingredients: [
      "500 g Mehl",
      "1 Päckchen Trockenhefe",
      "300 ml lauwarmes Wasser",
      "2 EL Olivenöl",
      "1 TL Salz",
      "1 TL Zucker"
    ]
  },
  {
    name: "Wraps mit Hühnchen",
    description: "Weiche Tortilla-Wraps gefüllt mit Hühnchen und Gemüse.",
    ingredients: [
      "4 große Tortillas",
      "300 g Hähnchenbrust, in Streifen",
      "1 Paprika, in Streifen",
      "Salatblätter",
      "Joghurt-Dressing",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Bulgur-Salat",
    description: "Frischer Salat mit Bulgur, Gemüse und Kräutern.",
    ingredients: [
      "150 g Bulgur",
      "200 ml Gemüsebrühe",
      "1 Gurke, gewürfelt",
      "2 Tomaten, gewürfelt",
      "1 Bund Minze, gehackt",
      "3 EL Olivenöl",
      "Saft einer Zitrone",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Kartoffelsuppe",
    description: "Cremige Suppe aus Kartoffeln und Lauch.",
    ingredients: [
      "500 g Kartoffeln, gewürfelt",
      "1 Lauchstange, in Ringe",
      "1 Zwiebel, gehackt",
      "1 Liter Gemüsebrühe",
      "100 ml Sahne",
      "2 EL Butter",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Schupfnudeln mit Sauerkraut",
    description: "Gebratene Schupfnudeln mit würzigem Sauerkraut.",
    ingredients: [
      "400 g Schupfnudeln",
      "300 g Sauerkraut",
      "1 Zwiebel, gehackt",
      "2 EL Öl",
      "Salz, Pfeffer, Kümmel"
    ]
  },
  {
    name: "Vegetarische Chili-Bowl",
    description: "Würziges Chili mit Bohnen, Mais und Reis.",
    ingredients: [
      "1 Dose Kidneybohnen (ca. 400 g), abgetropft",
      "1 Dose Mais (ca. 300 g), abgetropft",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "1 Dose gehackte Tomaten (400 g)",
      "150 g Reis",
      "2 EL Öl",
      "Salz, Pfeffer, Chili"
    ]
  },
  {
    name: "Süßkartoffel-Pommes",
    description: "Knusprige Pommes aus Süßkartoffeln aus dem Ofen.",
    ingredients: [
      "500 g Süßkartoffeln",
      "2 EL Olivenöl",
      "Salz, Paprikapulver"
    ]
  },
  {
    name: "Shakshuka",
    description: "Würziges Tomaten-Gemüse mit pochierten Eiern.",
    ingredients: [
      "4 Eier",
      "1 Dose gehackte Tomaten (400 g)",
      "1 Zwiebel, gehackt",
      "1 Paprika, gewürfelt",
      "2 Knoblauchzehen, gepresst",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Paprikapulver, Kreuzkümmel"
    ]
  },
  {
    name: "Frühlingsrollen",
    description: "Knusprige Rollen mit Gemüsefüllung.",
    ingredients: [
      "10 Reispapierblätter",
      "150 g Karotten, geraspelt",
      "100 g Glasnudeln, vorgekocht",
      "100 g Kohl, fein geschnitten",
      "2 EL Sojasoße",
      "Öl zum Frittieren"
    ]
  },
  {
    name: "Rindfleisch-Bowl",
    description: "Schüssel mit gebratenem Rindfleisch, Reis und Gemüse.",
    ingredients: [
      "300 g Rindfleisch, dünn geschnitten",
      "150 g Reis",
      "1 Brokkoli, in Röschen",
      "1 Karotte, in Scheiben",
      "2 EL Sojasoße",
      "1 EL Sesamöl",
      "1 Knoblauchzehe, gepresst"
    ]
  },
  {
    name: "Maultaschen",
    description: "Schwäbische Teigtaschen mit Fleischfüllung.",
    ingredients: [
      "300 g Mehl",
      "3 Eier",
      "300 g gemischtes Hackfleisch",
      "1 Zwiebel, gehackt",
      "1 Bund Petersilie, gehackt",
      "Salz, Pfeffer, Muskatnuss"
    ]
  },
  {
    name: "Zucchini-Puffer",
    description: "Knusprige Puffer aus geraspelter Zucchini.",
    ingredients: [
      "2 große Zucchini, geraspelt",
      "1 Ei",
      "3 EL Mehl",
      "1 Zwiebel, fein gehackt",
      "Salz und Pfeffer",
      "Öl zum Braten"
    ]
  },
  {
    name: "Paella",
    description: "Spanisches Reisgericht mit Meeresfrüchten und Gemüse.",
    ingredients: [
      "250 g Paella-Reis",
      "200 g Garnelen",
      "150 g Hähnchenfleisch, gewürfelt",
      "1 rote Paprika, gewürfelt",
      "100 g Erbsen",
      "1 Zwiebel, gehackt",
      "1 Knoblauchzehe, gepresst",
      "750 ml Hühnerbrühe",
      "2 EL Olivenöl",
      "Safran, Salz, Pfeffer"
    ]
  },
  {
    name: "Kürbissuppe",
    description: "Cremige Suppe aus Hokkaido-Kürbis.",
    ingredients: [
      "800 g Hokkaido-Kürbis, gewürfelt",
      "1 Zwiebel, gehackt",
      "1 Kartoffel, gewürfelt",
      "750 ml Gemüsebrühe",
      "100 ml Sahne",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Muskat"
    ]
  },
  {
    name: "Tiramisu",
    description: "Klassisches italienisches Dessert mit Mascarpone und Espresso.",
    ingredients: [
      "250 g Mascarpone",
      "3 Eier",
      "100 g Zucker",
      "150 ml Espresso, abgekühlt",
      "200 g Löffelbiskuits",
      "Kakaopulver zum Bestreuen"
    ]
  },
  {
    name: "Bulgursalat Taboulé",
    description: "Frischer Salat mit Bulgur, Tomaten und Minze.",
    ingredients: [
      "150 g Bulgur",
      "200 ml kochendes Wasser",
      "2 Tomaten, gewürfelt",
      "1 Bund Petersilie, gehackt",
      "1 Bund Minze, gehackt",
      "3 EL Olivenöl",
      "Saft einer Zitrone",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Shawarma Wrap",
    description: "Würziges Fleisch im Fladenbrot mit Salat.",
    ingredients: [
      "300 g Hähnchenbrust, gewürzt",
      "4 Fladenbrote",
      "Salat, Tomaten, Gurken",
      "Knoblauchsoße oder Joghurt-Dressing"
    ]
  },
  {
    name: "Caprese-Sandwich",
    description: "Frisches Sandwich mit Tomate, Mozzarella und Basilikum.",
    ingredients: [
      "2 Scheiben Ciabatta",
      "2 Scheiben Mozzarella",
      "2 Tomatenscheiben",
      "Frische Basilikumblätter",
      "2 EL Pesto",
      "Olivenöl"
    ]
  },
  {
    name: "Vegetarische Pizza",
    description: "Pizza mit Gemüse und Käse.",
    ingredients: [
      "Pizzateig (selbstgemacht oder gekauft)",
      "200 g passierte Tomaten",
      "1 Zucchini, in Scheiben",
      "1 Paprika, gewürfelt",
      "100 g Champignons, geschnitten",
      "150 g geriebener Mozzarella",
      "Olivenöl, Salz, Pfeffer"
    ]
  },
  {
    name: "Porridge mit Früchten",
    description: "Warmer Haferbrei mit frischem Obst.",
    ingredients: [
      "50 g Haferflocken",
      "300 ml Milch oder Pflanzendrink",
      "1 EL Honig",
      "Frische Beeren oder Banane"
    ]
  },
  {
    name: "Fischfilet mit Gemüse",
    description: "Gedünstetes Fischfilet mit buntem Gemüse.",
    ingredients: [
      "2 Fischfilets (z.B. Kabeljau)",
      "1 Zucchini, gewürfelt",
      "1 Karotte, gewürfelt",
      "1 Paprika, gewürfelt",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Zitronensaft"
    ]
  },
  {
    name: "Ratatouille",
    description: "Geschmortes Gemüse der Provence.",
    ingredients: [
      "1 Aubergine, gewürfelt",
      "1 Zucchini, gewürfelt",
      "1 Paprika, gewürfelt",
      "2 Tomaten, gewürfelt",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "3 EL Olivenöl",
      "Thymian, Salz, Pfeffer"
    ]
  },
  {
    name: "French Toast",
    description: "Süße, in Ei getunkte Brotscheiben, gebraten.",
    ingredients: [
      "4 Scheiben Toastbrot",
      "2 Eier",
      "100 ml Milch",
      "1 TL Zimt",
      "Butter zum Braten",
      "Ahornsirup oder Puderzucker"
    ]
  },
  {
    name: "Gulasch",
    description: "Deftiger Eintopf mit Rindfleisch und Paprika.",
    ingredients: [
      "500 g Rindfleisch, gewürfelt",
      "2 Zwiebeln, gehackt",
      "2 Paprika, gewürfelt",
      "2 EL Paprikapulver",
      "500 ml Rinderbrühe",
      "2 EL Öl",
      "Salz, Pfeffer"
    ]
  },
  {
    name: "Bohneneintopf",
    description: "Herzhafter Eintopf mit weißen Bohnen und Gemüse.",
    ingredients: [
      "400 g weiße Bohnen (vorgekocht)",
      "2 Karotten, gewürfelt",
      "1 Stange Sellerie, gewürfelt",
      "1 Zwiebel, gehackt",
      "1 Liter Gemüsebrühe",
      "2 EL Tomatenmark",
      "Salz, Pfeffer, Thymian"
    ]
  },
  {
    name: "Avocado Toast",
    description: "Geröstetes Brot mit zerdrückter Avocado.",
    ingredients: [
      "2 Scheiben Vollkornbrot",
      "1 reife Avocado",
      "Salz, Pfeffer",
      "Chiliflocken (optional)",
      "Zitronensaft"
    ]
  },
  {
    name: "Shrimps-Pasta",
    description: "Pasta mit Knoblauch-Shrimps und frischen Kräutern.",
    ingredients: [
      "200 g Spaghetti",
      "200 g Shrimps",
      "2 Knoblauchzehen, gehackt",
      "2 EL Olivenöl",
      "1 Bund Petersilie, gehackt",
      "Salz, Pfeffer",
      "1 Zitrone"
    ]
  },
  {
    name: "Minestrone",
    description: "Italienische Gemüsesuppe mit Pasta.",
    ingredients: [
      "1 Zwiebel, gehackt",
      "2 Karotten, gewürfelt",
      "2 Stangen Sellerie, gewürfelt",
      "1 Zucchini, gewürfelt",
      "1 Dose gehackte Tomaten",
      "100 g kleine Pasta (z.B. Ditalini)",
      "1 Liter Gemüsebrühe",
      "Salz, Pfeffer, Basilikum"
    ]
  },
  {
    name: "Zimtschnecken",
    description: "Süße Hefeschnecken mit Zimt und Zucker.",
    ingredients: [
      "500 g Mehl",
      "250 ml Milch",
      "75 g Zucker",
      "75 g Butter",
      "1 Würfel Hefe",
      "2 EL Zimt",
      "50 g Zucker (für Füllung)"
    ]
  },
  {
    name: "Falafel",
    description: "Frittierte Bällchen aus Kichererbsen und Kräutern.",
    ingredients: [
      "250 g Kichererbsen (über Nacht eingeweicht)",
      "1 Zwiebel",
      "2 Knoblauchzehen",
      "1 Bund Petersilie",
      "1 TL Kreuzkümmel",
      "Salz und Pfeffer",
      "Öl zum Frittieren"
    ]
  },
  {
    name: "Grüner Smoothie",
    description: "Frischer Smoothie mit Spinat, Banane und Apfel.",
    ingredients: [
      "1 Handvoll Spinat",
      "1 Banane",
      "1 Apfel",
      "200 ml Wasser",
      "1 EL Honig (optional)"
    ]
  },
  {
    name: "Kartoffelgratin",
    description: "Überbackene Kartoffeln mit Sahne und Käse.",
    ingredients: [
      "800 g Kartoffeln, in dünne Scheiben",
      "200 ml Sahne",
      "150 g geriebener Käse",
      "1 Knoblauchzehe",
      "Salz, Pfeffer, Muskatnuss"
    ]
  },
  {
    name: "Bauernfrühstück",
    description: "Bratkartoffeln mit Ei und Zwiebeln.",
    ingredients: [
      "400 g Kartoffeln, gekocht und gewürfelt",
      "4 Eier",
      "1 Zwiebel, gewürfelt",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Bruschetta",
    description: "Geröstetes Brot mit Tomaten und Basilikum.",
    ingredients: [
      "4 Scheiben Ciabatta",
      "3 Tomaten, gewürfelt",
      "2 Knoblauchzehen",
      "3 EL Olivenöl",
      "Basilikumblätter",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Quinoa-Salat",
    description: "Gesunder Salat mit Quinoa und Gemüse.",
    ingredients: [
      "150 g Quinoa",
      "200 ml Gemüsebrühe",
      "1 Paprika, gewürfelt",
      "1 Gurke, gewürfelt",
      "1 Bund Koriander, gehackt",
      "3 EL Olivenöl",
      "Saft einer Zitrone",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Kichererbsen-Curry",
    description: "Würziges Curry mit Kichererbsen und Kokosmilch.",
    ingredients: [
      "1 Dose Kichererbsen (ca. 400 g)",
      "1 Zwiebel, gewürfelt",
      "2 Knoblauchzehen, gepresst",
      "2 EL Currypaste",
      "200 ml Kokosmilch",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  }
];

export default function Home() {
  const [searchTerm, setSearchTerm] = useState("");
  const [filteredRecipes, setFilteredRecipes] = useState(recipes);
  const [dailyRecipe, setDailyRecipe] = useState(null);

  useEffect(() => {
    // Tägliches Rezept vorschlagen
    const index = Math.floor(Math.random() * recipes.length);
    setDailyRecipe(recipes[index]);
  }, []);

  useEffect(() => {
    if (searchTerm.trim() === "") {
      setFilteredRecipes(recipes);
    } else {
      const lower = searchTerm.toLowerCase();
      setFilteredRecipes(
        recipes.filter(
          r =>
            r.name.toLowerCase().includes(lower) ||
            r.ingredients.some(ing => ing.toLowerCase().includes(lower)) ||
            r.description.toLowerCase().includes(lower)
        )
      );
    }
  }, [searchTerm]);

  return (
    <div style={styles.page}>
      <header style={styles.header}>
        <h1 style={{ color: "#fff" }}>Kochkompass 🍳</h1>
        <input
          style={styles.searchInput}
          type="text"
          placeholder="Suche Rezepte..."
          value={searchTerm}
          onChange={e => setSearchTerm(e.target.value)}
          autoFocus
        />
      </header>

      <main style={styles.main}>
        {dailyRecipe && (
          <section style={styles.dailyRecipe}>
            <h2>Täglicher Vorschlag</h2>
            <h3>{dailyRecipe.name}</h3>
            <p>{dailyRecipe.description}</p>
            <strong>Zutaten:</strong>
            <ul>
              {dailyRecipe.ingredients.map((ing, i) => (
                <li key={i}>{ing}</li>
              ))}
            </ul>
          </section>
        )}

        <section style={styles.recipeList}>
          <h2>Alle Rezepte ({filteredRecipes.length})</h2>
          {filteredRecipes.length === 0 && (
            <p>Keine Rezepte gefunden. Bitte Suchbegriff anpassen.</p>
          )}
          {filteredRecipes.map((recipe, i) => (
            <article key={i} style={styles.recipeCard}>
              <h3>{recipe.name}</h3>
              <p>{recipe.description}</p>
              <strong>Zutaten:</strong>
              <ul>
                {recipe.ingredients.map((ing, j) => (
                  <li key={j}>{ing}</li>
                ))}
              </ul>
            </article>
          ))}
        </section>
      </main>

      <footer style={styles.footer}>
        <small>© 2025 Kochkompass</small>
      </footer>
    </div>
  );
}

const styles = {
  page: {
    fontFamily: "'Segoe UI', Tahoma, Geneva, Verdana, sans-serif",
    background:
      "linear-gradient(135deg, #f6d365 0%, #fda085 50%, #f6d365 100%)",
    minHeight: "100vh",
    padding: "0",
    margin: "0",
    display: "flex",
    flexDirection: "column",
    alignItems: "center",
  },
  header: {
    backgroundColor: "#ff6f61",
    width: "100%",
    padding: "1rem 2rem",
    boxShadow: "0 4px 6px rgba(0,0,0,0.1)",
    display: "flex",
    justifyContent: "space-between",
    alignItems: "center",
    flexWrap: "wrap",
  },
  searchInput: {
    fontSize: "1rem",
    padding: "0.5rem 1rem",
    borderRadius: "20px",
    border: "none",
    outline: "none",
    width: "250px",
    maxWidth: "100%",
  },
  main: {
    maxWidth: "900px",
    width: "100%",
    padding: "1rem 2rem",
    flex: "1",
  },
  dailyRecipe: {
    backgroundColor: "#fff3f0",
    padding: "1rem 1.5rem",
    borderRadius: "12px",
    boxShadow: "0 2px 8px rgba(0,0,0,0.1)",
    marginBottom: "2rem",
  },
  recipeList: {
    backgroundColor: "#fff",
    borderRadius: "12px",
    padding: "1rem 1.5rem",
    boxShadow: "0 2px 8px rgba(0,0,0,0.1)",
  },
  recipeCard: {
    borderBottom: "1px solid #eee",
    padding: "0.75rem 0",
  },
  footer: {
    width: "100%",
    textAlign: "center",
    padding: "1rem 0",
    backgroundColor: "#ff6f61",
    color: "#fff",
    marginTop: "auto",
  },
};
