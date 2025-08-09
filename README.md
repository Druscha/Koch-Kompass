# Koch-Kompass
Entdecke täglich neue Rezepte, plane deine Mahlzeiten clever und erstelle blitzschnell deine persönliche Einkaufsliste – alles an einem Ort. So macht Kochen und Einkaufen Spaß und geht super einfach!

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
    name: "Caesar Salad",
    description: "Frischer Salat mit Caesar-Dressing, Croutons und Parmesan.",
    ingredients: [
      "1 Kopf Römersalat, gewaschen",
      "50 g Croutons",
      "30 g Parmesan, gehobelt",
      "3 EL Caesar-Dressing",
      "1 Hähnchenbrustfilet, gegrillt und in Scheiben",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Pancakes",
    description: "Fluffige Pfannkuchen, perfekt zum Frühstück.",
    ingredients: [
      "150 g Mehl",
      "2 EL Zucker",
      "1 TL Backpulver",
      "1 Prise Salz",
      "200 ml Milch",
      "1 Ei",
      "2 EL geschmolzene Butter",
      "Butter oder Öl zum Braten",
      "Ahornsirup oder Früchte zum Servieren"
    ]
  },
  {
    name: "Gemüsepfanne mit Tofu",
    description: "Bunte Pfanne mit knackigem Gemüse und proteinreichem Tofu.",
    ingredients: [
      "200 g Tofu, gewürfelt",
      "1 rote Paprika, in Streifen",
      "1 Zucchini, in Scheiben",
      "100 g Brokkoli-Röschen",
      "2 EL Sojasoße",
      "1 EL Sesamöl",
      "1 Knoblauchzehe, gepresst",
      "Frischer Ingwer (ca. 1 cm), fein gerieben"
    ]
  },
  {
    name: "Tomatensuppe",
    description: "Würzige Suppe aus frischen Tomaten und Kräutern.",
    ingredients: [
      "500 g reife Tomaten, gehackt",
      "1 Zwiebel, gehackt",
      "1 Knoblauchzehe",
      "500 ml Gemüsebrühe",
      "2 EL Olivenöl",
      "Salz und Pfeffer",
      "Frisches Basilikum zum Garnieren"
    ]
  },
  {
    name: "Rührei mit Kräutern",
    description: "Leichtes Frühstück mit frischen Kräutern.",
    ingredients: [
      "3 Eier",
      "50 ml Milch",
      "Salz und Pfeffer",
      "1 EL Butter",
      "Frische Petersilie und Schnittlauch, gehackt"
    ]
  },
  {
    name: "Ofenkartoffeln mit Kräuterquark",
    description: "Knusprige Kartoffeln aus dem Ofen mit frischem Quark.",
    ingredients: [
      "4 große Kartoffeln",
      "2 EL Olivenöl",
      "Salz und Paprikapulver",
      "250 g Quark",
      "Frische Kräuter (Schnittlauch, Petersilie), gehackt",
      "1 Knoblauchzehe, gepresst"
    ]
  },
  {
    name: "Vegetarische Lasagne",
    description: "Schichtweise Lasagne mit Gemüse und Käse.",
    ingredients: [
      "9 Lasagneblätter",
      "400 g passierte Tomaten",
      "1 Zucchini, gewürfelt",
      "1 Aubergine, gewürfelt",
      "1 rote Paprika, gewürfelt",
      "200 g Mozzarella, gerieben",
      "50 g Parmesan, gerieben",
      "2 EL Olivenöl",
      "Salz, Pfeffer, italienische Kräuter"
    ]
  },
  {
    name: "Quinoa-Salat mit Feta",
    description: "Frischer Salat mit Quinoa, Gemüse und Feta-Käse.",
    ingredients: [
      "150 g Quinoa",
      "200 ml Gemüsebrühe",
      "1 Gurke, gewürfelt",
      "150 g Kirschtomaten, halbiert",
      "100 g Feta, gewürfelt",
      "2 EL Olivenöl",
      "Saft einer Zitrone",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Chili con Carne",
    description: "Würziges Gericht mit Hackfleisch, Bohnen und Mais.",
    ingredients: [
      "300 g Rinderhackfleisch",
      "1 Dose Kidneybohnen (ca. 400 g), abgetropft",
      "1 Dose Mais (ca. 300 g), abgetropft",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "1 Dose gehackte Tomaten (400 g)",
      "2 EL Tomatenmark",
      "1 TL Paprikapulver",
      "1 TL Kreuzkümmel",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Linsensuppe",
    description: "Herzhafte Suppe mit roten Linsen und Gemüse.",
    ingredients: [
      "200 g rote Linsen",
      "1 Karotte, gewürfelt",
      "1 Stange Sellerie, gewürfelt",
      "1 Zwiebel, gehackt",
      "1 Knoblauchzehe, gepresst",
      "1 Liter Gemüsebrühe",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Lorbeerblatt"
    ]
  },
  {
    name: "Fischfilet mit Kartoffelsalat",
    description: "Knuspriges Fischfilet mit cremigem Kartoffelsalat.",
    ingredients: [
      "2 Fischfilets (z.B. Seelachs, je ca. 150 g)",
      "400 g Kartoffeln",
      "1 kleine Zwiebel, fein gehackt",
      "2 EL Mayonnaise",
      "1 EL Senf",
      "2 EL Essig",
      "Salz und Pfeffer",
      "Petersilie zum Garnieren"
    ]
  },
  {
    name: "Ratatouille",
    description: "Französisches Gemüsegericht aus Zucchini, Auberginen und Tomaten.",
    ingredients: [
      "1 Zucchini, gewürfelt",
      "1 Aubergine, gewürfelt",
      "2 Tomaten, gewürfelt",
      "1 rote Paprika, gewürfelt",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "3 EL Olivenöl",
      "Salz, Pfeffer, Kräuter der Provence"
    ]
  },
  {
    name: "Gebratener Reis mit Gemüse",
    description: "Leckeres Pfannengericht mit Reis und buntem Gemüse.",
    ingredients: [
      "200 g gekochter Reis",
      "1 Karotte, gewürfelt",
      "100 g Erbsen",
      "1 Frühlingszwiebel, gehackt",
      "2 Eier",
      "2 EL Sojasoße",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Hähnchenbrust mit Ofengemüse",
    description: "Saftige Hähnchenbrust mit bunt gemischtem Gemüse aus dem Ofen.",
    ingredients: [
      "2 Hähnchenbrustfilets (je ca. 150 g)",
      "200 g Karotten, in Stifte geschnitten",
      "150 g Zucchini, in Scheiben",
      "1 Paprika, gewürfelt",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Paprikapulver"
    ]
  },
  {
    name: "Gulasch",
    description: "Deftiges Rindergulasch mit Paprika und Zwiebeln.",
    ingredients: [
      "400 g Rindfleisch, gewürfelt",
      "2 Zwiebeln, grob gehackt",
      "2 Paprika, gewürfelt",
      "2 EL Tomatenmark",
      "500 ml Rinderbrühe",
      "2 EL Öl",
      "Salz, Pfeffer, Paprikapulver"
    ]
  },
  {
    name: "Veggie-Burger",
    description: "Leckere vegetarische Burger-Patties mit frischem Gemüse.",
    ingredients: [
      "1 Dose Kichererbsen (ca. 400 g), abgetropft",
      "1 kleine Zwiebel, gehackt",
      "1 Knoblauchzehe, gepresst",
      "50 g Haferflocken",
      "1 Ei",
      "1 TL Kreuzkümmel",
      "Salz und Pfeffer",
      "Burger-Brötchen, Salat, Tomaten, Gurken"
    ]
  },
  {
    name: "Spinatlasagne",
    description: "Cremige Lasagne mit Spinat und Ricotta.",
    ingredients: [
      "9 Lasagneblätter",
      "300 g Blattspinat (frisch oder TK)",
      "250 g Ricotta",
      "200 ml Bechamelsauce",
      "150 g geriebener Mozzarella",
      "2 Knoblauchzehen, gepresst",
      "Salz, Pfeffer, Muskatnuss"
    ]
  },
  {
    name: "Tomaten-Mozzarella-Salat",
    description: "Einfacher Salat mit frischen Tomaten, Mozzarella und Basilikum.",
    ingredients: [
      "3 große Tomaten, in Scheiben",
      "150 g Mozzarella, in Scheiben",
      "Frische Basilikumblätter",
      "2 EL Olivenöl",
      "1 EL Balsamico-Essig",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Chili sin Carne",
    description: "Vegetarisches Chili mit Bohnen und Gemüse.",
    ingredients: [
      "1 Dose Kidneybohnen (ca. 400 g), abgetropft",
      "1 Dose Mais (ca. 300 g), abgetropft",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "1 Dose gehackte Tomaten (400 g)",
      "2 EL Tomatenmark",
      "1 TL Paprikapulver",
      "1 TL Kreuzkümmel",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Omelett mit Gemüse",
    description: "Fluffiges Omelett mit buntem Gemüse.",
    ingredients: [
      "3 Eier",
      "50 ml Milch",
      "1 kleine Paprika, gewürfelt",
      "1 Tomate, gewürfelt",
      "1 Frühlingszwiebel, gehackt",
      "Salz und Pfeffer",
      "1 EL Butter"
    ]
  },
  {
    name: "Pasta Alfredo",
    description: "Cremige Pasta mit Parmesan und Sahnesoße.",
    ingredients: [
      "200 g Pasta (z.B. Fettuccine)",
      "150 ml Sahne",
      "50 g Parmesan, gerieben",
      "2 EL Butter",
      "1 Knoblauchzehe, gepresst",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Gemüsesuppe",
    description: "Wärmende Suppe mit saisonalem Gemüse.",
    ingredients: [
      "2 Karotten, gewürfelt",
      "1 Stange Sellerie, gewürfelt",
      "1 Lauchstange, in Ringe",
      "1 Kartoffel, gewürfelt",
      "1 Zwiebel, gehackt",
      "1 Liter Gemüsebrühe",
      "2 EL Olivenöl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Beef Stroganoff",
    description: "Rindergeschnetzeltes in cremiger Pilzsoße.",
    ingredients: [
      "300 g Rindfleisch, in Streifen",
      "150 g Champignons, geschnitten",
      "1 Zwiebel, gehackt",
      "150 ml saure Sahne",
      "2 EL Öl",
      "Salz, Pfeffer, Paprikapulver"
    ]
  },
  {
    name: "Falafel mit Tahini-Sauce",
    description: "Knusprige Kichererbsenbällchen mit Sesamsoße.",
    ingredients: [
      "250 g Kichererbsen (über Nacht eingeweicht)",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen",
      "1 Bund Petersilie",
      "1 TL Kreuzkümmel",
      "Salz und Pfeffer",
      "Öl zum Frittieren",
      "Tahini, Zitronensaft, Wasser für die Sauce"
    ]
  },
  {
    name: "Hähnchen-Pfanne mit Paprika",
    description: "Schnelle Pfanne mit Hähnchen und buntem Paprika.",
    ingredients: [
      "300 g Hähnchenbrust, gewürfelt",
      "2 Paprika (rot und gelb), in Streifen",
      "1 Zwiebel, gehackt",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Paprikapulver"
    ]
  },
  {
    name: "Minestrone",
    description: "Italienische Gemüsesuppe mit Nudeln und Bohnen.",
    ingredients: [
      "1 Zucchini, gewürfelt",
      "2 Karotten, gewürfelt",
      "1 Dose weiße Bohnen (ca. 400 g), abgetropft",
      "100 g kleine Pasta",
      "1 Zwiebel, gehackt",
      "1 Liter Gemüsebrühe",
      "2 EL Olivenöl",
      "Salz, Pfeffer, italienische Kräuter"
    ]
  },
  {
    name: "Kaiserschmarrn",
    description: "Fluffiger österreichischer Pfannkuchen mit Rosinen.",
    ingredients: [
      "3 Eier",
      "200 ml Milch",
      "150 g Mehl",
      "1 EL Zucker",
      "1 Prise Salz",
      "50 g Rosinen",
      "Butter zum Braten",
      "Puderzucker zum Bestreuen",
      "Apfelmus oder Zwetschgenröster zum Servieren"
    ]
  },
  {
    name: "Zucchini-Nudeln mit Pesto",
    description: "Leichtes Gericht mit Zucchini als Nudeln und frischem Pesto.",
    ingredients: [
      "2 große Zucchini",
      "4 EL Pesto (Basilikum oder Rucola)",
      "20 g Parmesan, gerieben",
      "1 EL Olivenöl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Gemüse-Curry",
    description: "Cremiges Curry mit buntem Gemüse und Kokosmilch.",
    ingredients: [
      "1 Brokkoli, in Röschen",
      "1 rote Paprika, gewürfelt",
      "1 Karotte, in Scheiben",
      "200 ml Kokosmilch",
      "2 EL Currypaste",
      "1 Zwiebel, gehackt",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Ratatouille-Quiche",
    description: "Herzhafte Quiche mit Ratatouille-Gemüsefüllung.",
    ingredients: [
      "1 Mürbeteigboden",
      "200 g Ratatouille-Gemüse (Zucchini, Aubergine, Paprika)",
      "3 Eier",
      "150 ml Sahne",
      "100 g geriebener Käse",
      "Salz, Pfeffer, Kräuter"
    ]
  },
  {
    name: "Kartoffelgratin",
    description: "Überbackene Kartoffeln mit Sahne und Käse.",
    ingredients: [
      "800 g Kartoffeln, in dünne Scheiben",
      "200 ml Sahne",
      "150 g geriebener Käse",
      "2 Knoblauchzehen, gepresst",
      "Salz, Pfeffer, Muskatnuss"
    ]
  },
  {
    name: "Nudelsalat",
    description: "Kalter Salat mit Nudeln, Gemüse und Dressing.",
    ingredients: [
      "250 g kurze Nudeln (z.B. Fusilli)",
      "1 rote Paprika, gewürfelt",
      "1 Gurke, gewürfelt",
      "100 g Mais",
      "3 EL Mayonnaise",
      "2 EL Joghurt",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Rote Bete Salat",
    description: "Frischer Salat mit Roter Bete und Ziegenkäse.",
    ingredients: [
      "300 g Rote Bete (vorgekocht), gewürfelt",
      "100 g Ziegenkäse",
      "1 Apfel, gewürfelt",
      "2 EL Walnüsse, gehackt",
      "3 EL Olivenöl",
      "1 EL Balsamico-Essig",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Gnocchi mit Tomatensoße",
    description: "Weiche Kartoffelgnocchi in fruchtiger Tomatensoße.",
    ingredients: [
      "400 g Gnocchi",
      "400 ml passierte Tomaten",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "2 EL Olivenöl",
      "Basilikum, Salz und Pfeffer"
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
      "250 ml Milch oder Pflanzendrink",
      "1 TL Honig",
      "Frische Beeren oder Bananenscheiben"
    ]
  },
  {
    name: "Frikadellen",
    description: "Deftige Fleischklöße mit Zwiebeln.",
    ingredients: [
      "400 g gemischtes Hackfleisch",
      "1 kleine Zwiebel, fein gehackt",
      "1 Ei",
      "2 EL Semmelbrösel",
      "Salz, Pfeffer, Muskat"
    ]
  },
  {
    name: "Tomatenreis",
    description: "Reis mit fruchtigen Tomaten und Gewürzen.",
    ingredients: [
      "200 g Reis",
      "1 Dose gehackte Tomaten (400 g)",
      "1 Zwiebel, gehackt",
      "1 Knoblauchzehe, gepresst",
      "2 EL Olivenöl",
      "Salz, Pfeffer, Paprikapulver"
    ]
  },
  {
    name: "Hähnchen-Caesar-Wrap",
    description: "Wrap gefüllt mit Hähnchen, Salat und Caesar-Dressing.",
    ingredients: [
      "4 große Tortillas",
      "300 g Hähnchenbrust, gegrillt und in Streifen",
      "1 Kopf Römersalat",
      "50 g Parmesan, gehobelt",
      "4 EL Caesar-Dressing"
    ]
  },
  {
    name: "Linsen-Dal",
    description: "Indisches Gericht mit roten Linsen und Gewürzen.",
    ingredients: [
      "200 g rote Linsen",
      "1 Zwiebel, gehackt",
      "2 Knoblauchzehen, gepresst",
      "1 Stück Ingwer (2 cm), gerieben",
      "400 ml Kokosmilch",
      "1 EL Currypulver",
      "2 EL Öl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Kartoffelpuffer",
    description: "Knusprige Puffer aus geriebenen Kartoffeln.",
    ingredients: [
      "500 g Kartoffeln, gerieben",
      "1 Ei",
      "2 EL Mehl",
      "Salz und Pfeffer",
      "Öl zum Braten"
    ]
  },
  {
    name: "Sushi Bowl",
    description: "Reis mit rohem Fisch, Gemüse und Sojasoße.",
    ingredients: [
      "150 g Sushi-Reis",
      "200 g Lachsfilet, roh oder geräuchert",
      "1 Avocado, in Scheiben",
      "1 Gurke, in Streifen",
      "Sojasoße",
      "Sesam"
    ]
  },
  {
    name: "Frittata mit Gemüse",
    description: "Italienisches Omelett mit Gemüse und Käse.",
    ingredients: [
      "6 Eier",
      "100 ml Milch",
      "1 Zucchini, gewürfelt",
      "1 Paprika, gewürfelt",
      "100 g geriebener Käse",
      "Salz und Pfeffer",
      "2 EL Olivenöl"
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
      "2 EL Olivenöl",
      "Salz und Pfeffer"
    ]
  },
  {
    name: "Pasta Pesto",
    description: "Schnelle Pasta mit grünem Pesto.",
    ingredients: [
      "200 g Pasta",
      "4 EL Pesto",
      "30 g Parmesan, gerieben",
      "2 EL Olivenöl"
    ]
  },
  {
    name: "Bunte Gemüsepfanne",
    description: "Gebratenes Gemüse mit Sojasoße und Sesam.",
    ingredients: [
      "1 Brokkoli, in Röschen",
      "1 rote Paprika, gewürfelt
