
# Gombo161.github.io<!DOCTYPE html>
<html lang="de"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Anatomle – Anatomie raten</title>
<style>
:root{--bg:#f6f7f9;--card:#fff;--tx:#1b1f24;--mut:#6a7380;--bd:#d9dde3;--ok:#2e7d32;--no:#c62828;--ac:#3b6fd4;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#14171b;--card:#1e2328;--tx:#e8ebef;--mut:#98a2b0;--bd:#343b44;--ok:#388e3c;--no:#b3261e;--ac:#6b9bf0;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#14171b;--card:#1e2328;--tx:#e8ebef;--mut:#98a2b0;--bd:#343b44;--ok:#388e3c;--no:#b3261e;--ac:#6b9bf0;color-scheme:dark}
*{box-sizing:border-box}html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--bg);color:var(--tx);font:16px/1.4 system-ui,-apple-system,"Segoe UI",Roboto,sans-serif}
main{max-width:720px;margin:0 auto;padding:16px 12px 40px}
header{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
h1{font-size:1.5rem;margin:0}h1 span{color:var(--ac)}
button{font:inherit;cursor:pointer;border:1px solid var(--bd);background:var(--card);color:var(--tx);border-radius:10px;padding:8px 12px}
button.p{background:var(--ac);color:#fff;border-color:var(--ac)}
.bar{display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:10px}
.wrap{position:relative;flex:1;min-width:200px}
input{width:100%;font:inherit;padding:10px 12px;border-radius:10px;border:1px solid var(--bd);background:var(--card);color:var(--tx)}
#sug{position:absolute;left:0;right:0;top:100%;z-index:5;background:var(--card);border:1px solid var(--bd);border-radius:10px;margin-top:4px;max-height:260px;overflow:auto;display:none}
#sug div{padding:8px 12px;cursor:pointer;display:flex;justify-content:space-between}
#sug div:hover,#sug div.a{background:var(--bg)}#sug small{color:var(--mut)}
#msg{min-height:1.4em;color:var(--no);font-size:.9rem;margin:2px 0 8px}
.g{display:grid;grid-template-columns:1.2fr 1.1fr 1.9fr .85fr 1fr;gap:4px;margin-bottom:4px}
.g>div{padding:8px 3px;border-radius:8px;font-size:.66rem;text-align:center;display:flex;flex-direction:column;justify-content:center;min-height:52px;color:#fff;overflow-wrap:break-word;hyphens:auto;line-height:1.2;animation:pop .35s ease both}
.g.h>div{background:none;color:var(--mut);min-height:0;padding:2px;animation:none;font-weight:600}
.g>div:nth-child(2){animation-delay:.08s}.g>div:nth-child(3){animation-delay:.16s}.g>div:nth-child(4){animation-delay:.24s}.g>div:nth-child(5){animation-delay:.32s}
.g .n{background:var(--card);color:var(--tx);border:1px solid var(--bd)}.g .n small{color:var(--mut)}
.ok{background:var(--ok)}.no{background:var(--no)}
@keyframes pop{from{transform:rotateX(90deg);opacity:0}to{transform:none;opacity:1}}
.end{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:14px;margin:12px 0;text-align:center}
dialog{background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:14px;max-width:460px;width:calc(100% - 24px)}
dialog::backdrop{background:#0008}
.sw{display:inline-block;width:14px;height:14px;border-radius:3px;vertical-align:middle}
#body{display:block;margin:0 auto;width:100%;max-width:340px;height:auto}
#body{--s1:#f0dcc8;--s2:#d3ab8c}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]) #body{--s1:#6e5a4c;--s2:#4b3b31}}
:root[data-theme="dark"] #body{--s1:#6e5a4c;--s2:#4b3b31}
#body .ol{fill:#8d6a53;stroke:#8d6a53;stroke-width:2.5;stroke-linejoin:round}
#body .sk{fill:url(#sk);stroke:none}
#body .dt{fill:none;stroke:#000;stroke-opacity:.22;stroke-width:1;stroke-linecap:round}
#body g ellipse{fill:var(--c);fill-opacity:.3;stroke:var(--c);stroke-opacity:.6;stroke-width:.8}
#body g.hit ellipse{fill:#ff2a2a;fill-opacity:.9;stroke:#ff2a2a;stroke-opacity:1;filter:drop-shadow(0 0 5px #ff2a2a)}
#body g.win ellipse{fill:#1fe05a;fill-opacity:.95;stroke:#1fe05a;stroke-opacity:1;filter:drop-shadow(0 0 8px #1fe05a)}
</style></head><body><main>
<header><h1>Anat<span>omle</span></h1><div><button id="bs">📊</button> <button id="bh">❓</button></div></header>
<div class="bar"><div class="wrap"><input id="in" placeholder="Muskel, Knochen, Organ … (deutsch oder lateinisch)" autocomplete="off"><div id="sug"></div></div>
<button class="p" id="go">Raten</button></div>
<div id="msg"></div>
<div class="bar"><span id="left" style="color:var(--mut)"></span><span style="flex:1"></span><button id="rnd">🎲 Zufälliges Rätsel</button></div>
<div class="g h"><div>Name</div><div>Distanz</div><div>Klasse</div><div>Region</div><div>Typ</div></div>
<div id="rows"></div><div id="end"></div>
<h3 style="margin:20px 0 4px">Anatomie-Modell</h3>
<p style="margin:0 0 8px;color:var(--mut);font-size:.85rem">🔴 deine Tipps leuchten rot · 🟢 die Lösung leuchtet grün, sobald du sie triffst</p>
<svg id="body" viewBox="0 0 300 740" role="img" aria-label="Anatomie-Modell des Körpers"><defs><linearGradient id="sk" gradientUnits="userSpaceOnUse" x1="0" y1="0" x2="300" y2="0"><stop offset="0" style="stop-color:var(--s2)"/><stop offset=".5" style="stop-color:var(--s1)"/><stop offset="1" style="stop-color:var(--s2)"/></linearGradient><g id="hf"><path d="M222 232C244 228 262 240 267 266C270 296 273 330 273 354C274 384 282 404 284 420C292 436 294 456 292 480L290 496Q280 504 268 496C266 480 264 462 264 440L264 424C254 400 246 380 243 354C240 326 232 300 228 284Z"/><path d="M150 168L166 172C167 196 170 208 180 214C200 220 214 226 224 234L226 282C223 312 215 336 212 358C213 384 222 406 228 430C230 450 232 470 229 490C226 505 220 512 218 520C222 535 222 545 220 556C216 575 212 590 212 600C214 612 222 620 222 628Q222 634 214 634L186 634Q178 634 178 628C178 618 182 612 184 600C182 585 180 570 178 556C178 545 180 535 182 520C178 505 172 490 170 470C166 462 158 462 150 462Z"/><path d="M150 70C176 70 190 94 190 122C190 140 184 156 176 166C170 174 160 180 150 180ZM190 112C199 110 201 132 191 140Z"/></g></defs><use href="#hf" class="ol"/><use href="#hf" class="ol" transform="translate(300 0) scale(-1 1)"/><use href="#hf" class="sk"/><use href="#hf" class="sk" transform="translate(300 0) scale(-1 1)"/><path id="dtl" class="dt"/><g id="bodyst"></g></svg>
<dialog id="dh"><h3>So geht’s</h3>
<p>Errate die gesuchte Struktur in 8 Versuchen. Nach jedem Tipp siehst du:</p>
<p><b>Distanz (warm/kalt):</b> je wärmer (🔥) und röter, desto näher liegt dein Tipp räumlich am Ziel; blau/🧊 heißt weit weg. Der Pfeil zeigt, in welche Richtung das Ziel von deinem Tipp aus liegt (• = ungefähr auf gleicher Höhe). Das Symbol daneben zeigt das System (z. B. 🫁 Atmung). Im Anatomie-Modell unten leuchten deine Tipps rot und die gesuchte Struktur leuchtet grün, sobald du sie getroffen hast.</p>
<p><b>Klasse (Körpersystem), Region, Typ:</b> <span class="sw ok"></span> ✓ stimmt überein, <span class="sw no"></span> ✗ weicht ab.</p>
<p>Tippen kannst du alle Strukturen der Datenbank, gesucht werden aber nur bekannte. Täglich ein neues Rätsel, oder übe mit dem Zufalls-Button.</p><button onclick="dh.close()">Schließen</button></dialog>
<dialog id="ds"><h3>Statistik</h3><div id="st"></div><button onclick="ds.close()">Schließen</button></dialog>
</main>
<script>
const RAW=`Schädel|Cranium|B|K|B|0|18|0
Stirnbein|Os frontale|B|K|B|0|18.5|1
Scheitelbein|Os parietale|B|K|B|2|19|0
Hinterhauptbein|Os occipitale|B|K|B|0|17.5|-1.5
Schläfenbein|Os temporale|B|K|B|3|17.5|0
Keilbein|Os sphenoidale|B|K|B|0|17.5|.5
Siebbein|Os ethmoidale|B|K|B|0|17.5|1
Oberkiefer|Maxilla|B|K|B|0|16.8|1.2
Unterkiefer|Mandibula|B|K|B|0|16|1
Jochbein|Os zygomaticum|B|K|B|2.5|17.2|1
Nasenbein|Os nasale|B|K|B|0|17.3|1.4
Zungenbein|Os hyoideum|B|H|B|0|15|.8
Atlas|Atlas|B|H|B|0|15.8|-.5
Axis|Axis|B|H|B|0|15.3|-.5
Halswirbel|Vertebrae cervicales|B|H|B|0|14.5|-.5
Brustwirbel|Vertebrae thoracicae|B|R|B|0|11.5|-1
Lendenwirbel|Vertebrae lumbales|B|R|B|0|9|-1
Kreuzbein|Os sacrum|B|R|B|0|7|-1.2
Steißbein|Os coccygis|B|R|B|0|6|-1.2
Brustbein|Sternum|B|R|B|0|12|1.5
Rippen|Costae|B|R|B|3|11.5|0
Schlüsselbein|Clavicula|B|R|B|3|13.5|1
Schulterblatt|Scapula|B|A|B|4|13|-1.2
Oberarmknochen|Humerus|B|A|B|5.5|11.5|0
Speiche|Radius|B|A|B|6.5|8.5|.3
Elle|Ulna|B|A|B|6.7|8.5|-.3
Handwurzelknochen|Ossa carpi|B|A|B|7|6.8|0
Mittelhandknochen|Ossa metacarpi|B|A|B|7.2|6.2|0
Fingerglieder|Phalanges manus|B|A|B|7.3|5.2|0
Beckenknochen|Os coxae|B|R|B|3|7.5|0
Oberschenkelknochen|Femur|B|U|B|3|5.5|0
Kniescheibe|Patella|B|U|B|2.8|3.8|1
Schienbein|Tibia|B|U|B|2.5|2|.4
Wadenbein|Fibula|B|U|B|3.2|2|0
Sprungbein|Talus|B|U|B|2.5|.6|0
Fersenbein|Calcaneus|B|U|B|2.5|.2|-1
Mittelfußknochen|Ossa metatarsi|B|U|B|2.5|.1|1
Zehenglieder|Phalanges pedis|B|U|B|2.5|0|1.5
Trapezmuskel|M. trapezius|M|R|B|2|13.5|-1.3
Deltamuskel|M. deltoideus|M|A|B|5|13|0
Großer Brustmuskel|M. pectoralis major|M|R|B|2.5|12|1.5
Kleiner Brustmuskel|M. pectoralis minor|M|R|B|3|12.3|1.2
Breiter Rückenmuskel|M. latissimus dorsi|M|R|B|3|10.5|-1.5
Sägezahnmuskel|M. serratus anterior|M|R|B|4|11|.5
Zwerchfell|Diaphragma|M|R|B|0|10.3|0
Gerader Bauchmuskel|M. rectus abdominis|M|R|B|.8|9|1.5
Äußerer schräger Bauchmuskel|M. obliquus externus|M|R|B|3.5|9|1
Rückenstrecker|M. erector spinae|M|R|B|1.2|10|-1.5
Bizeps|M. biceps brachii|M|A|B|5.5|11|.6
Trizeps|M. triceps brachii|M|A|B|5.5|11|-.6
Oberarmmuskel|M. brachialis|M|A|B|5.5|10.5|.3
Speichenseitiger Handbeuger|M. flexor carpi radialis|M|A|B|6.5|8.5|.4
Kopfwender|M. sternocleidomastoideus|M|H|B|1.5|14.5|.5
Kaumuskel|M. masseter|M|K|B|2.5|16.3|.8
Schläfenmuskel|M. temporalis|M|K|B|3|17.5|.3
Augenringmuskel|M. orbicularis oculi|M|K|B|1.2|17.5|1.5
Großer Gesäßmuskel|M. gluteus maximus|M|U|B|3|7|-1.5
Mittlerer Gesäßmuskel|M. gluteus medius|M|U|B|3.5|7.8|-1
Lenden-Darmbein-Muskel|M. iliopsoas|M|R|B|1.5|7.5|.3
Schneidermuskel|M. sartorius|M|U|B|3|5.5|1
Vierköpfiger Oberschenkelmuskel|M. quadriceps femoris|M|U|B|3|5.5|1
Zweiköpfiger Oberschenkelmuskel|M. biceps femoris|M|U|B|3|5.5|-1
Langer Adduktor|M. adductor longus|M|U|B|1.8|5.5|.3
Zwillingswadenmuskel|M. gastrocnemius|M|U|B|2.8|2.8|-1
Schollenmuskel|M. soleus|M|U|B|2.8|2.2|-.8
Vorderer Schienbeinmuskel|M. tibialis anterior|M|U|B|2.6|2.2|1
Herzmuskelgewebe|Myocardium|G|R|K|.5|11.5|1
Achillessehne|Tendo calcaneus|G|U|B|2.5|.8|-1
Bandscheibe|Discus intervertebralis|G|R|B|0|10|-.5
Meniskus|Meniscus|G|U|B|2.8|3.7|.5
Vorderes Kreuzband|Lig. cruciatum anterius|G|U|B|2.8|3.7|.2
Gehirn|Cerebrum|O|K|N|0|18|0
Kleinhirn|Cerebellum|O|K|N|0|17|-1.2
Hirnanhangdrüse|Hypophyse|O|K|E|0|17.3|.3
Auge|Oculus|O|K|S|1.3|17.5|1.6
Ohr|Auris|O|K|S|3.5|17|0
Zunge|Lingua|O|K|V|0|16|1
Kehlkopf|Larynx|O|H|A|0|14.8|.8
Schilddrüse|Glandula thyroidea|O|H|E|0|14|.8
Luftröhre|Trachea|O|H|A|0|13.5|.5
Speiseröhre|Oesophagus|O|R|V|0|12|0
Lunge|Pulmo|O|R|A|2.5|12|0
Herz|Cor|O|R|K|.8|11.5|1
Thymus|Thymus|O|R|I|0|12.8|1
Leber|Hepar|O|R|V|-2.5|10|.8
Gallenblase|Vesica fellea|O|R|V|-2|9.5|1
Magen|Gaster|O|R|V|2|10|.8
Milz|Splen|O|R|I|3.5|10|-.5
Bauchspeicheldrüse|Pancreas|O|R|V|0|9.5|0
Zwölffingerdarm|Duodenum|O|R|V|-1|9.3|.3
Dünndarm|Intestinum tenue|O|R|V|0|8.3|.8
Dickdarm|Colon|O|R|V|0|8.5|.5
Blinddarm|Caecum|O|R|V|-2.5|7.5|.8
Mastdarm|Rectum|O|R|V|0|6.3|-.5
Niere|Ren|O|R|U|2|9.8|-1
Nebenniere|Glandula suprarenalis|O|R|E|1.5|10.6|-.9
Harnleiter|Ureter|O|R|U|1.5|8|-.5
Harnblase|Vesica urinaria|O|R|U|0|6.8|1
Gebärmutter|Uterus|O|R|U|0|7|.5
Prostata|Prostata|O|R|U|0|6.3|.7
Hodensack|Scrotum|O|R|U|0|5.3|1.2
Aorta|Aorta|V|R|K|0|11|.2
Untere Hohlvene|Vena cava inferior|V|R|K|-1|9.5|-.2
Halsschlagader|Arteria carotis|V|H|K|1.2|15|.5
Oberschenkelarterie|Arteria femoralis|V|U|K|2.5|6|.8
Ischiasnerv|Nervus ischiadicus|N|U|N|3|6|-1.2
Rückenmark|Medulla spinalis|O|R|N|0|11|-.8
Speichennerv|Nervus radialis|N|A|N|6|10|-.3
Vagusnerv|Nervus vagus|N|H|N|1|14.5|.3
Armgeflecht|Plexus brachialis|N|H|N|3|13.5|0
Wirbelsäule|Columna vertebralis|B|R|B|0|11|-1
Schultergelenk|Articulatio humeri|J|A|B|4.5|13|0
Ellenbogengelenk|Articulatio cubiti|J|A|B|6|9.5|0
Handgelenk|Articulatio radiocarpalis|J|A|B|6.9|7.2|0
Fingergelenke|Articulationes digitorum|J|A|B|7.3|5.5|0
Hüftgelenk|Articulatio coxae|J|U|B|3|7|0
Kniegelenk|Articulatio genus|J|U|B|2.8|3.8|.3
Sprunggelenk|Articulatio talocruralis|J|U|B|2.5|.8|0
Kiefergelenk|Articulatio temporomandibularis|J|K|B|3|16.8|0
Iliosakralgelenk|Articulatio sacroiliaca|J|R|B|1.5|7.3|-1
Schambeinfuge|Symphysis pubica|J|R|B|0|6.8|1.3
Zähne|Dentes|O|K|V|0|16.4|1.3
Augenhöhle|Orbita|B|K|S|1.3|17.5|1.3
Darmbein|Os ilium|B|R|B|3.5|8|-.3
Sitzbein|Os ischii|B|R|B|2.5|6.7|-.5
Schambein|Os pubis|B|R|B|1|6.9|1
Hörknöchelchen|Ossicula auditus|B|K|S|3.3|17|0
Kahnbein|Os scaphoideum|B|A|B|6.9|6.9|0
Fußwurzelknochen|Ossa tarsi|B|U|B|2.5|.5|.3
Schwertfortsatz|Processus xiphoideus|B|R|B|0|10.6|1.5
Rippenknorpel|Cartilago costalis|G|R|B|1.5|11.2|1.4
Rautenmuskel|M. rhomboideus|M|R|B|1.5|12.5|-1.3
Obergrätenmuskel|M. supraspinatus|M|A|B|3|13.5|-1.3
Untergrätenmuskel|M. infraspinatus|M|A|B|3.5|12.8|-1.4
Großer Rundmuskel|M. teres major|M|A|B|4|12|-1.3
Unterschulterblattmuskel|M. subscapularis|M|A|B|3.8|12.5|-.8
Innerer schräger Bauchmuskel|M. obliquus internus|M|R|B|3|8.8|.8
Querer Bauchmuskel|M. transversus abdominis|M|R|B|2.5|8.7|.5
Quadratus lumborum|M. quadratus lumborum|M|R|B|1.5|9|-1
Zwischenrippenmuskeln|Mm. intercostales|M|R|B|3|11.5|.8
Armspeichenmuskel|M. brachioradialis|M|A|B|6.3|9.5|.5
Rundmuskel des Unterarms|M. pronator teres|M|A|B|6|9.8|.4
Fingerstrecker|M. extensor digitorum|M|A|B|6.5|8.5|-.5
Fingerbeuger|M. flexor digitorum|M|A|B|6.5|8.3|.5
Daumenballen|Thenar|M|A|B|7|6.2|.3
Halbsehnenmuskel|M. semitendinosus|M|U|B|2.5|5.5|-1
Schlankmuskel|M. gracilis|M|U|B|2|5|.2
Kammmuskel|M. pectineus|M|U|B|2|6.5|.8
Oberschenkelbinden-Spanner|M. tensor fasciae latae|M|U|B|4|7|.8
Birnenmuskel|M. piriformis|M|U|B|2|7|-1.2
Hinterer Schienbeinmuskel|M. tibialis posterior|M|U|B|2.5|2.2|-.3
Langer Wadenbeinmuskel|M. fibularis longus|M|U|B|3.2|2.5|0
Halshautmuskel|Platysma|M|H|B|1|15|1.2
Stirnmuskel|M. frontalis|M|K|B|1|18.5|1.3
Mundringmuskel|M. orbicularis oris|M|K|B|0|16.3|1.6
Großer Jochbeinmuskel|M. zygomaticus major|M|K|B|2|16.7|1.4
Beckenboden|Diaphragma pelvis|M|R|B|0|6.5|0
Mandeln|Tonsillae|O|K|I|0|16.3|.4
Speicheldrüse|Glandula parotis|O|K|V|3|16.5|.6
Nase|Nasus|O|K|A|0|17|1.8
Nasennebenhöhlen|Sinus paranasales|O|K|A|1|17.5|1.2
Rachen|Pharynx|O|K|A|0|15.8|.5
Hörschnecke|Cochlea|O|K|S|3|17|0
Netzhaut|Retina|G|K|S|1.3|17.5|1.2
Hornhaut|Cornea|G|K|S|1.3|17.5|1.7
Bronchien|Bronchi|O|R|A|1.5|12.5|.3
Lungenbläschen|Alveoli|G|R|A|2.5|12|0
Brustfell|Pleura|G|R|A|3|11.5|.3
Herzbeutel|Pericardium|G|R|K|.8|11.5|1.1
Mitralklappe|Valva mitralis|G|R|K|1|11.3|.8
Zirbeldrüse|Glandula pinealis|O|K|E|0|17.8|-.3
Hypothalamus|Hypothalamus|O|K|E|0|17.4|.2
Nebenschilddrüse|Glandula parathyroidea|O|H|E|0|14|.3
Bauchfell|Peritoneum|G|R|V|0|8.5|1.2
Großes Netz|Omentum majus|G|R|V|0|8|1.2
Wurmfortsatz|Appendix vermiformis|O|R|V|-2.5|7.3|.8
Krummdarm|Ileum|O|R|V|-1|7.5|.8
Leerdarm|Jejunum|O|R|V|1.5|8.5|.8
After|Anus|O|R|V|0|5.8|-1
Hoden|Testis|O|R|U|.8|5.3|1.2
Nebenhoden|Epididymis|O|R|U|.8|5.2|1.2
Penis|Penis|O|R|U|0|5.8|1.8
Eierstock|Ovarium|O|R|U|2|7.3|.4
Eileiter|Tuba uterina|O|R|U|1.5|7.4|.4
Scheide|Vagina|O|R|U|0|6.2|.5
Harnröhre|Urethra|O|R|U|0|6|.9
Brustdrüse|Glandula mammaria|O|R|U|2.5|12|1.7
Lymphknoten|Nodi lymphatici|O|H|I|1.5|14.5|.3
Knochenmark|Medulla ossium|G|U|I|3|5.5|0
Lungenarterie|Truncus pulmonalis|V|R|K|.5|12|1
Pfortader|Vena portae|V|R|K|-.8|9.8|.3
Nierenarterie|Arteria renalis|V|R|K|1|9.8|-.5
Armarterie|Arteria brachialis|V|A|K|5.5|10.5|.2
Speichenarterie|Arteria radialis|V|A|K|6.5|8|.3
Kniekehlenarterie|Arteria poplitea|V|U|K|2.8|3.8|-.5
Halsvene|Vena jugularis|V|H|K|1.3|15|.4
Große Rosenvene|Vena saphena magna|V|U|K|2|4|.6
Sehnerv|Nervus opticus|N|K|S|.8|17.5|.5
Gesichtsnerv|Nervus facialis|N|K|N|2.5|16.8|.8
Dreigeminusnerv|Nervus trigeminus|N|K|N|2|17.2|1
Mittelarmnerv|Nervus medianus|N|A|N|6.3|9|.3
Ellennerv|Nervus ulnaris|N|A|N|6.7|9.5|-.4
Oberschenkelnerv|Nervus femoralis|N|U|N|2.5|6.3|.7
Wadenbeinnerv|Nervus fibularis|N|U|N|3.2|3.3|0
Schienbeinnerv|Nervus tibialis|N|U|N|2.7|3|-.5
Zwerchfellnerv|Nervus phrenicus|N|H|N|1.5|13|.2
Lendengeflecht|Plexus lumbalis|N|R|N|1.5|8.5|-.8
Kreuzgeflecht|Plexus sacralis|N|R|N|1|7|-1
Hirnhaut|Meninges|G|K|N|0|18.5|0
Großhirnrinde|Cortex cerebri|G|K|N|0|18.8|.3
Hirnstamm|Truncus encephali|O|K|N|0|16.5|-.5
Balken|Corpus callosum|G|K|N|0|18|0
Vulva|Vulva|O|R|U|0|5.8|1.6
Schamlippen|Labia pudendi|G|R|U|0|5.7|1.5
Kitzler|Clitoris|O|R|U|0|6|1.7
Hand|Manus|T|A|B|7.1|6|0
Finger|Digiti manus|T|A|B|7.3|5|0
Daumen|Pollex|T|A|B|6.6|6.2|.8
Fingernagel|Unguis manus|T|A|H|7.3|4.6|.3
Fuß|Pes|T|U|B|2.5|.3|1
Zehen|Digiti pedis|T|U|B|2.5|0|1.6
Großzeh|Hallux|T|U|B|1.7|0|1.6
Zehennagel|Unguis pedis|T|U|H|2.5|0|1.8
Haare|Capilli|T|K|H|0|19.4|-.2
Kopfhaut|Scalpus|G|K|H|0|19.2|.3
Schweißdrüsen|Glandulae sudoriferae|O|A|H|4|12.2|0
Talgdrüsen|Glandulae sebaceae|O|K|H|0|16.8|1.7
Milchbrustgang|Ductus thoracicus|V|R|I|-.4|10|-.5
Lymphgefäße|Vasa lymphatica|V|U|I|1.8|4|.4`;
const K={B:"Knochen",M:"Muskel",O:"Organ",G:"Gewebe",V:"Gefäß",N:"Nerv"},
R={K:"Kopf",H:"Hals",R:"Rumpf",A:"Obere Extr.",U:"Untere Extr."},
S={B:"Bewegung",A:"Atmung",V:"Verdauung",K:"Kreislauf",N:"Nerven",U:"Urogenital",E:"Hormone",S:"Sinne",I:"Immun"};
const DB=RAW.split("\n").map(l=>{const a=l.split("|");return{n:a[0],l:a[1],k:a[2],r:a[3],s:a[4],x:+a[5],y:+a[6],z:+a[7]}});
const $=id=>document.getElementById(id),MAX=8;
const norm=s=>s.toLowerCase().replace(/ä/g,"a").replace(/ö/g,"o").replace(/ü/g,"u").replace(/ß/g,"ss").replace(/[^a-z0-9 ]/g,"");
let T,G=[],over=false,daily=true,sel=-1,cur=[];
function start(d){daily=d;G=[];over=false;$("end").innerHTML="";$("rows").innerHTML="";clearBody();$("msg").textContent="";$("in").value="";
 if(d){const n=Math.floor(Date.now()/864e5);T=POOL[(n*7919+13)%POOL.length]}else T=POOL[Math.floor(Math.random()*POOL.length)];upd()}
function upd(){$("left").textContent="Versuche übrig: "+(MAX-G.length)}
function sug(){const q=norm($("in").value.trim());const box=$("sug");
 if(!q){box.style.display="none";cur=[];return}
 cur=DB.filter(e=>!G.includes(e)&&(norm(e.n).includes(q)||norm(e.l).includes(q))).slice(0,8);sel=-1;
 box.innerHTML=cur.map((e,i)=>`<div data-i="${i}">${e.n}<small>${e.l}</small></div>`).join("");
 box.style.display=cur.length?"block":"none"}
$("in").addEventListener("input",sug);
$("sug").addEventListener("mousedown",e=>{const d=e.target.closest("div[data-i]");if(d){e.preventDefault();$("in").value=cur[+d.dataset.i].n;$("sug").style.display="none";guess()}});
$("in").addEventListener("keydown",e=>{
 if(e.key==="ArrowDown"||e.key==="ArrowUp"){e.preventDefault();sel=(sel+(e.key==="ArrowDown"?1:-1)+cur.length)%Math.max(cur.length,1);[...$("sug").children].forEach((c,i)=>c.classList.toggle("a",i===sel))}
 if(e.key==="Enter"){if(sel>=0&&cur[sel])$("in").value=cur[sel].n;guess()}});
document.addEventListener("click",e=>{if(!e.target.closest(".wrap"))$("sug").style.display="none"});
$("go").onclick=guess;
function guess(){if(over)return;const q=norm($("in").value.trim());
 let g=DB.find(e=>norm(e.n)===q||norm(e.l)===q);if(!g&&cur.length===1)g=cur[0];
 const m=$("msg");$("sug").style.display="none";
 if(!g){m.textContent="Unbekannter Begriff – bitte aus der Liste wählen.";return}
 if(G.includes(g)){m.textContent="Das hast du schon getippt.";return}
 m.textContent="";G.push(g);mark(g,"hit");$("in").value="";addRow(g);upd();
 if(g===T)finish(true);else if(G.length>=MAX)finish(false)}
function dist(a,b){return Math.hypot(a.x-b.x,a.y-b.y,(a.z-b.z)*2)}
function pct(g){return Math.max(0,Math.round(100*(1-dist(g,T)/20)))}
function arrows(g){if(g===T)return"🎯";const dx=T.x-g.x,dy=T.y-g.y,dz=T.z-g.z;let a=[];
 if(Math.abs(dy)>1)a.push(dy>0?"↑":"↓");if(Math.abs(dx)>1)a.push(dx>0?"→":"←");if(Math.abs(dz)>.8)a.push(dz>0?"vorn":"hinten");return a.join(" ")}
function cell(ok,t){return `<div class="${ok?"ok":"no"}">${ok?"✓":"✗"} ${t}</div>`}
const SI={B:"🦴",A:"🫁",V:"🍽️",K:"🫀",N:"🧠",U:"💧",E:"⚗️",S:"👁️",I:"🛡️"};
function lab(p,g){return g===T?"🎯 Treffer":p>=90?"🔥 Heiß":p>=75?"Sehr warm":p>=60?"Warm":p>=45?"Lauwarm":p>=30?"Kalt":"🧊 Eiskalt"}
function model(g){const cx=(10+g.x*1.3).toFixed(1),cy=(38-g.y*1.8).toFixed(1);
 return `<svg width="26" height="52" viewBox="0 0 20 40" aria-hidden="true"><g fill="#fff" fill-opacity=".35"><circle cx="10" cy="4.5" r="3.5"/><rect x="5" y="9" width="10" height="16" rx="3"/><rect x="16" y="10" width="3.5" height="15" rx="1.5"/><rect x=".5" y="10" width="3.5" height="15" rx="1.5"/><rect x="5.5" y="25" width="4" height="14" rx="1.5"/><rect x="10.5" y="25" width="4" height="14" rx="1.5"/></g><circle cx="${cx}" cy="${cy}" r="2.6" fill="#fff" stroke="#000" stroke-width=".8"/></svg>`}
function addRow(g){const p=pct(g),h=Math.round(220-p*2.2);
 const r=document.createElement("div");r.className="g";
 r.innerHTML=`<div class="n"><b>${g.n}</b><small>${g.l}</small></div><div style="background:hsl(${h} 60% 34%);flex-direction:row;align-items:center;justify-content:center;gap:4px"><span><b>${lab(p,g)}</b><br>${arrow(g)} ${SI[g.s]}</span></div>`+
 cell(g.s===T.s,S[g.s])+cell(g.r===T.r,R[g.r])+cell(g.k===T.k,K[g.k]);
 $("rows").appendChild(r)}
function share(w){const sq=G.map(g=>{const p=pct(g);return(p>=75?"🟩":p>=45?"🟨":"🟥")+(g.k===T.k?"🟩":"🟥")+(g.r===T.r?"🟩":"🟥")+(g.s===T.s?"🟩":"🟥")}).join("\n");
 return`Anatomle ${daily?new Date().toLocaleDateString("de-DE"):"(Übung)"} ${w?G.length:"X"}/${MAX}\n${sq}`}
function stats(w){if(!daily)return;try{const s=JSON.parse(localStorage.getItem("anatomle")||"{}");s.p=(s.p||0)+1;s.w=(s.w||0)+(w?1:0);s.s=w?(s.s||0)+1:0;s.b=Math.max(s.b||0,s.s);localStorage.setItem("anatomle",JSON.stringify(s))}catch(e){}}
function finish(w){over=true;stats(w);mark(T,"win");
 $("end").innerHTML=`<div class="end"><h3>${w?"🎉 Richtig in "+G.length+" Versuchen!":"Leider verloren"}</h3><p>Gesucht: <b>${T.n}</b> (${T.l}) – ${K[T.k]}, ${R[T.r]}</p><button class="p" id="sh">Ergebnis kopieren</button> <button id="nx">Neues Übungsrätsel</button></div>`;
 $("sh").onclick=()=>{const t=share(w);(navigator.clipboard?navigator.clipboard.writeText(t):Promise.reject()).then(()=>$("sh").textContent="Kopiert ✓").catch(()=>{prompt("Zum Kopieren:",t)})};
 $("nx").onclick=()=>start(false)}
$("rnd").onclick=()=>start(false);
$("bh").onclick=()=>$("dh").showModal();
$("bs").onclick=()=>{let s={};try{s=JSON.parse(localStorage.getItem("anatomle")||"{}")}catch(e){}
 const p=s.p||0;$("st").innerHTML=`<p>Gespielt: <b>${p}</b><br>Siegquote: <b>${p?Math.round(100*(s.w||0)/p):0} %</b><br>Aktuelle Serie: <b>${s.s||0}</b><br>Beste Serie: <b>${s.b||0}</b></p><p style="color:var(--mut);font-size:.85rem">Nur Tagesrätsel zählen.</p>`;$("ds").showModal()};
const SZD={B:[6,6],M:[9,15],O:[13,13],G:[7,7],V:[4,16],N:[3.5,16]},COL={B:"#9aa3ad",M:"#d0605a",O:"#e3a05c",G:"#7f93d6",V:"#c0392b",N:"#d4b020"};
const SZ={"Schädel":[24,28],"Stirnbein":[14,8],"Scheitelbein":[12,10],"Hinterhauptbein":[14,10],"Schläfenbein":[7,9],"Unterkiefer":[16,8],"Oberkiefer":[12,6],"Halswirbel":[6,14],"Atlas":[7,4],"Axis":[6,4],"Brustwirbel":[6,24],"Lendenwirbel":[7,20],"Kreuzbein":[10,14],"Rippen":[16,28],"Brustbein":[5,22],"Schlüsselbein":[18,4],"Schulterblatt":[12,18],"Oberarmknochen":[5,34],"Speiche":[4,32],"Elle":[4,32],"Oberschenkelknochen":[7,48],"Schienbein":[5,44],"Wadenbein":[4,44],"Beckenknochen":[20,16],"Handwurzelknochen":[9,6],"Mittelhandknochen":[8,10],"Fingerglieder":[8,14],"Zehenglieder":[9,5],"Mittelfußknochen":[10,6],"Fersenbein":[8,6],"Sprungbein":[7,6],"Trapezmuskel":[24,26],"Deltamuskel":[14,14],"Großer Brustmuskel":[24,16],"Breiter Rückenmuskel":[22,34],"Gerader Bauchmuskel":[8,32],"Rückenstrecker":[8,40],"Bizeps":[8,24],"Trizeps":[8,24],"Vierköpfiger Oberschenkelmuskel":[15,52],"Zweiköpfiger Oberschenkelmuskel":[14,48],"Zwillingswadenmuskel":[11,28],"Schollenmuskel":[8,28],"Vorderer Schienbeinmuskel":[7,36],"Großer Gesäßmuskel":[20,20],"Lunge":[20,34],"Leber":[26,16],"Dünndarm":[28,24],"Dickdarm":[40,30],"Magen":[17,18],"Gehirn":[26,24],"Herz":[14,16],"Niere":[9,13],"Zwerchfell":[48,8],"Harnblase":[12,10],"Zunge":[11,6]};
const ASYM=["Leber","Gallenblase","Magen","Milz","Blinddarm","Herz","Zwölffingerdarm","Untere Hohlvene"],gm=new Map(),NS="http://www.w3.org/2000/svg";let order=[];
function detail(){let d="";for(const m of[1,-1]){const X=v=>(150+m*v).toFixed(0);
 d+=`M${X(4)} 224Q${X(40)} 214 ${X(72)} 234`;
 for(let i=0;i<4;i++){const y=268+i*16;d+=`M${X(8)} ${y}Q${X(46)} ${y+8} ${X(63)} ${y+28}`}
 d+=`M${X(6)} 292Q${X(38)} 302 ${X(60)} 270M${X(28)} 270m-3 0a3 3 0 1 0 6 0a3 3 0 1 0-6 0`;
 d+=`M${X(23)} 130m-8 0q8-6 16 0q-8 5-16 0M${X(32)} 118q${m*9}-6 ${m*18}-1`;
 d+=`M${X(6)} 318H${X(24)}M${X(6)} 342H${X(24)}M${X(6)} 366H${X(24)}M${X(32)} 316Q${X(36)} 345 ${X(30)} 400M${X(50)} 552m-10 0q10-12 20 0`}
 return d+"M150 300V420M150 138L146 156Q150 160 154 156M138 169Q150 175 162 169M150 378m-2 0a2 2 0 1 0 4 0a2 2 0 1 0-4 0"}
const Yd=h=>h>=7?620-28*h:424+(7-h)*40;
function buildBody(){const st=$("bodyst");document.querySelectorAll("#hf path").forEach(p=>{let i=0;p.setAttribute("d",p.getAttribute("d").replace(/\d+(\.\d+)?/g,n=>i++%2?(+n<424?+n:424+(+n-424)*10/7).toFixed(0):n))});$("dtl").setAttribute("d",detail());order=DB.map(e=>({e,s:SZ[e.n]||SZD[e.k]})).sort((a,b)=>b.s[0]*b.s[1]-a.s[0]*a.s[1]);
 order.forEach(o=>{const g=document.createElementNS(NS,"g");g.style.setProperty("--c",COL[o.e.k]);
  const xs=[150+o.e.x*18];if(Math.abs(o.e.x)>=1.2&&!ASYM.includes(o.e.n))xs.push(150-o.e.x*18);
  xs.forEach(cx=>{const el=document.createElementNS(NS,"ellipse");el.setAttribute("cx",cx);el.setAttribute("cy",Yd(o.e.y));el.setAttribute("rx",Math.max(o.s[0],5));el.setAttribute("ry",Math.max(o.s[1],5)*(o.e.y<7?10/7:1));g.appendChild(el)});
  st.appendChild(g);gm.set(o.e,g)})}
function mark(e,c){const g=gm.get(e);g.classList.add(c);$("bodyst").appendChild(g)}
function clearBody(){order.forEach(o=>{const g=gm.get(o.e);g.classList.remove("hit","win");$("bodyst").appendChild(g)})}
COL.B="#7d8793";K.J="Gelenk";K.T="Körperteil";COL.T="#c08a50";SZD.T=[7,7];
function arrow(g){if(g===T)return"🎯";const dx=T.x-g.x,dy=T.y-g.y,h=Math.abs(dx)>1?(dx>0?1:2):0,v=Math.abs(dy)>1?(dy>0?1:2):0;return[["•","↑","↓"],["→","↗","↘"],["←","↖","↙"]][h][v]}S.H="Haut und Hautanhangsgebilde";Object.assign(S,{B:"Bewegungsapparat",K:"Herz-Kreislauf-System",N:"Nervensystem",V:"Verdauungssystem",A:"Atmungssystem",U:"Urogenitalsystem",E:"Endokrines System",I:"Lymphatisches System"});DB.forEach(e=>{if(e.s==="S")e.s=e.k==="B"?"B":"N"});SI.H="🖐️";SZD.J=[7,7];COL.J="#6fb3b8";ASYM.push("Wurmfortsatz","Leerdarm");
Object.assign(SZ,{"Wirbelsäule":[5,60],"Darmbein":[14,12],"Zähne":[10,3],"Hirnstamm":[5,10],"Großhirnrinde":[24,22],"Hirnhaut":[27,27],"Nase":[5,7],"Bauchfell":[26,20],"Großes Netz":[22,10],"Brustfell":[20,30],"Lungenbläschen":[16,28],"Bronchien":[8,10],"Leerdarm":[10,14],"Krummdarm":[12,10],"Rippenknorpel":[10,8],"Beckenboden":[24,6]});
const KNOWN=new Set("Schädel,Unterkiefer,Wirbelsäule,Rippen,Brustbein,Schlüsselbein,Schulterblatt,Oberarmknochen,Elle,Speiche,Beckenknochen,Oberschenkelknochen,Kniescheibe,Schienbein,Wadenbein,Kreuzbein,Steißbein,Fersenbein,Halswirbel,Brustwirbel,Lendenwirbel,Bizeps,Trizeps,Deltamuskel,Großer Brustmuskel,Trapezmuskel,Gerader Bauchmuskel,Breiter Rückenmuskel,Großer Gesäßmuskel,Vierköpfiger Oberschenkelmuskel,Zwillingswadenmuskel,Achillessehne,Zwerchfell,Gehirn,Kleinhirn,Auge,Ohr,Nase,Zunge,Zähne,Mandeln,Luftröhre,Kehlkopf,Speiseröhre,Lunge,Herz,Leber,Gallenblase,Magen,Milz,Bauchspeicheldrüse,Dünndarm,Dickdarm,Blinddarm,Wurmfortsatz,Niere,Nebenniere,Harnblase,Gebärmutter,Eierstock,Scheide,Prostata,Hodensack,Hoden,Penis,After,Brustdrüse,Schilddrüse,Aorta,Rückenmark,Hirnhaut,Ischiasnerv,Bandscheibe,Meniskus,Vorderes Kreuzband,Kniegelenk,Schultergelenk,Hüftgelenk,Ellenbogengelenk,Handgelenk,Sprunggelenk,Hand,Fuß,Finger,Zehen,Vulva,Haare".split(",")),POOL=DB.filter(e=>KNOWN.has(e.n));
Object.assign(SZ,{"Vulva":[9,10],"Schamlippen":[8,12],"Kitzler":[5,5],"Hand":[13,22],"Finger":[10,12],"Daumen":[5,10],"Fingernagel":[5,4],"Fuß":[12,16],"Zehen":[11,5],"Großzeh":[5,5],"Zehennagel":[5,4],"Haare":[22,8],"Kopfhaut":[26,14],"Schweißdrüsen":[8,8],"Talgdrüsen":[8,8]});
buildBody();
start(true);
</script></body></html>
