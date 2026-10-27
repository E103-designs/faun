# E103 FAUN - Manuale prodotto

## Una utility, più possibilità
FAUN base assemblato. Schede MOD1-MOD6 opzionali.

FAUN è una utility passiva Eurorack configurabile: i sei jack vengono collegati attraverso jumper o cavi sul connettore posteriore. Non ha una funzione fissa per ciascun jack: il ruolo dipende dal cablaggio e dall’eventuale scheda MOD installata.

| BASE: CON JUMPER / CAVI | SOLO CON SCHEDA OPZIONALE |
| Splitter TRS, breakout CV/Gate, multipli passivi, adattamento MIDI TRS, breakout MIDI e collegamenti fra due FAUN. | Mixer stereo/mono, DAC R-2R, panning mixer, XOR/rettificatore e funzioni MOD6. |

Versione attuale: pannello nero, PCB viola, jack argentati, quattro corpi jack neri e due verde chiaro.

Il retro del prodotto reale

## Installazione e cavi
Configurare il retro prima di iniziare la patch.

Prima installazione

1. Spegni il sistema e scollega i cavi dai jack. Lavora fuori dal rack per accedere al retro.
2. Rimuovi i jumper della configurazione precedente e qualsiasi scheda MOD. Installa soltanto i ponti richiesti dalla modalità scelta.
3. Controlla le sigle X/Y/Z e i numeri 1-5; monta il modulo nel rack senza forzare i jack.
4. Collega prima una sola sorgente e prova un percorso alla volta a livello basso.

FAUN è passivo: non richiede alimentazione Eurorack. Il connettore 3 x 5 posteriore trasporta segnali e NON è un ingresso per il cavo di alimentazione a 10/16 pin.

TS e TRS non sono intercambiabili

| CAVO | CONTATTI | USO |
| TS mono | Tip = segnale; sleeve = massa | Jack 1, 2, 3, 4 e patch mono |
| TRS stereo | Tip = L; ring = R; sleeve = massa | A e B per audio stereo o due segnali separati |
| TRS MIDI | Tip/ring = coppia MIDI | Pinout Type A o B secondo il dispositivo |

Usa cavi TRS-TRS per raggiungere entrambi i contatti di A/B. Un cavo TS inserito in A/B mette il ring a massa. Non trattare un’uscita bilanciata TRS come una sorgente stereo senza verificarne il cablaggio.

Limiti del circuito passivo

Un multiple non somma le uscite di più apparecchi: collega una sorgente a più ingressi, non più uscite tra loro. Il carico può ridurre il livello o modificare una CV; per pitch 1 V/ottava preciso usa un multiple bufferizzato. FAUN non amplifica, non isola galvanicamente e non pilota direttamente diffusori passivi.

## La mappa dei 15 pin
Identifica i pin dalle serigrafie, non dal colore dei cavi.

La griglia è una vista logica del connettore: righe X, Y, Z e colonne 1-5. Sul prodotto può apparire ruotata. Leggi sempre le sigle della PCB prima di applicare un jumper; un jumper unisce soltanto i due pin indicati.

Links: 

| PIN | COLLEGAMENTO |
| X1 / X2 | A tip (L) / A ring (R) |
| X3 / X4 | B ring (R) / B tip (L) |
| X5 | Massa comune (sleeve) |
| Y1 = Z1 ... Y4 = Z4 | Tip dei jack mono 1 ... 4; ciascuna coppia è già unita sulla PCB |
| Y5 | Contatto normalizzato di 4 (4N) |
| Z5 | Contatto normalizzato di 2 (2N) |

Attenzione alla coppia B: nella griglia B Right viene prima di B Left. I pin 2N e 4N sono contatti di commutazione: sono collegati al tip del rispettivo jack quando questo è vuoto e si aprono inserendo una spina. Non sono due ulteriori uscite indipendenti.

I seguenti schemi mostrano i ponti in verde. Le righe e i numeri rimangono uguali in tutte le pagine. Per i ponti adiacenti usa jumper a due contatti; per distanze maggiori usa cavetti femmina-femmina del passo corretto (header da 2,54 mm).

## Due splitter TRS / CV-Gate
Modalità della base: 4 jumper, nessuna scheda MOD.

Links: X1-Y1, X2-Y2, X3-Y3, X4-Y4

| TRS | CONTATTO | JACK MONO |
| A | Tip / Left | 1 |
| A | Ring / Right | 2 |
| B | Tip / Left | 4 |
| B | Ring / Right | 3 |

Audio stereo

Collega una sorgente stereo ad A con un cavo TRS. Da 1 preleva L e da 2 preleva R con cavi TS. Per la seconda coppia usa B: L esce da 4 e R da 3. Il percorso può essere usato al contrario per riunire due segnali separati sui contatti tip/ring di una TRS; non è una somma mono.

Esempio: MPC con uscite CV/Gate doppie

Collega una porta TRS CV/Gate compatibile della MPC ad A: i due segnali saranno disponibili su 1 e 2. Una seconda porta può entrare in B e uscire su 4 (tip) e 3 (ring). Assegna pitch, gate o altre CV sulla MPC e collega ogni uscita mono alla destinazione corretta. Verifica il modello: non ogni MPC ha le stesse porte.

I jumper sono X1-Y1, X2-Y2, X3-Y3, X4-Y4. Non aggiungere i ponti della modalità multiple mentre separi due segnali indipendenti.

## Multipli passivi
Distribuire una sorgente a più destinazioni.

Due gruppi indipendenti 1 x 2

Links: X1-Y1, X4-Y4, Z1-Z2, Z3-Z4

Gruppo superiore: 1, 2 e A (tip). Gruppo inferiore: 3, 4 e B (tip). Per esempio: entra in A e preleva da 1 e 2; entra in B e preleva da 3 e 4. Usa cavi TS. È possibile scegliere qualsiasi jack del gruppo come ingresso, ma una sola sorgente per gruppo.

Un gruppo 1 x 5

Links: X1-Y1, X4-Y4, Z1-Z2, Z3-Z4, Y2-Y3

Aggiungi il ponte Y2-Y3 alla configurazione precedente: tutti i sei tip sono ora uniti. Collega una sorgente a un jack e fino a cinque destinazioni agli altri. I ring di A e B non sono parte del bus: questa è una distribuzione mono, non stereo.

Non usare queste configurazioni come mixer: unire direttamente due uscite attive può farle lavorare una contro l’altra. Per sommare segnali usa una scheda mixer dedicata.

## Adattatore MIDI TRS A / B
Scambiare tip e ring mantenendo la massa comune.

Links: X1-Y1, X2-Y2, X3-Y3, X4-Y4

Collegamento

1. Installa i quattro jumper della modalità splitter mostrati sopra.
2. Sul frontale collega 1 a 3 e 2 a 4 con due cavi TS.
3. Collega la sorgente MIDI ad A e la destinazione MIDI a B con cavi/adattatori TRS adatti ai due dispositivi.

| PERCORSO | RISULTATO |
| A tip > 1 > 3 > B ring | Tip e ring scambiati |
| A ring > 2 > 4 > B tip | Ring e tip scambiati |
| Sleeve A > massa comune > sleeve B | Massa mantenuta |

Per questo scambio i cavi frontali corretti sono 1-3 e 2-4. Con 1-4 e 2-3 il collegamento resta tip-tip e ring-ring: non avviene la conversione Type A/Type B.

FAUN modifica soltanto il cablaggio del connettore. Non converte MIDI in CV, non aggiunge MIDI USB, non fornisce un’interfaccia MIDI elettrica a un circuito che ne è privo. L’ingresso e l’uscita MIDI devono già essere presenti nei dispositivi collegati.

## Breakout MIDI + mult a 4 jack
Per moduli con header MIDI compatibile.

Links: Y2-Y3, Z1-Z2, Z3-Z4

I tre ponti mostrati uniscono soltanto 1, 2, 3 e 4 come multiple passivo a quattro jack (una sorgente più tre destinazioni). A e B rimangono separati per il MIDI. Non installare i jumper X-Y della pagina splitter.

Esempio verificabile: disting EX, Type A

| HEADER MIDI DEL DISTING EX | PIN FAUN | RUOLO |
| 1: OUT DIN 4 | X2 | A ring: MIDI Out |
| 2: OUT DIN 5 | X1 | A tip: MIDI Out |
| 3: IN DIN 5 | X4 | B tip: MIDI In |
| 4: IN DIN 4 | X3 | B ring: MIDI In |

A sistema spento, collega i quattro fili femmina-femmina al connettore GT4/MIDI del disting EX secondo la tabella. A diventa MIDI Out e B MIDI In per cavi Type A. Per Type B scambia i due fili della coppia interessata. Sul disting EX il pin 1 è vicino alla scritta GT4: verifica sempre il manuale della tua revisione.

Altri modelli non sono automaticamente equivalenti. Individua le funzioni OUT DIN4/5 e IN DIN5/4 nel loro manuale, poi abbinale ai contatti tip/ring di FAUN. Non collegare header di alimentazione, I2C o CV a caso. La massa/shield MIDI va gestita come indicato dal produttore del modulo sorgente.

## Signal mover e patchbay
Richiede due FAUN e cavetti posteriori.

Due FAUN possono trasferire segnali tra due punti del rack tramite cavetti interni. Spegni il sistema, togli jumper e MOD da entrambi e collega pin con la stessa funzione. Questa è una connessione passiva, senza isolamento né rigenerazione.

| PERCORSO | FAUN 1 > FAUN 2 |
| Mono 1 ... 4 | Y1 > Y1; Y2 > Y2; Y3 > Y3; Y4 > Y4 |
| Stereo A | X1 > X1 (tip); X2 > X2 (ring) |
| Stereo B | X4 > X4 (tip); X3 > X3 (ring) |
| Massa comune | X5 > X5 |

Esempio pratico

Collega un LFO al jack 1 del primo FAUN. Il segnale si ritrova sul jack 1 del secondo, da cui puoi raggiungere una destinazione vicina con un cavo corto. Ripeti sui canali 2, 3 e 4. Per due percorsi stereo, usa i collegamenti X della tabella e cavi TRS sui jack A e B.

Usarlo come punto di ripatching

Una volta riportati i segnali sul secondo FAUN, cambia i cavi sul suo frontale per distribuirli alle destinazioni desiderate. La tabella descrive una patchbay diretta, senza normalizzazioni aggiunte. I contatti Y5/Z5 non servono in questo collegamento di base.

Collega soltanto circuiti con massa di riferimento compatibile. Tieni i cavetti interni corti e lontani da parti metalliche esposte. Non unire due uscite di segnale sulle due estremità dello stesso percorso.

## Schede MOD opzionali
Le funzioni seguenti richiedono la scheda corrispondente.

Il FAUN base non contiene contemporaneamente tutti questi circuiti. Una scheda preset cambia la funzione dei jack; le MOD1-MOD6 sono accessori opzionali. Le tre funzioni della MOD6 si selezionano con i suoi jumper, non sono tre moduli indipendenti.

| SCHEDA | FUNZIONE | PAGINA |
| MOD1 | Mixer stereo passivo a 3 canali | 11 |
| MOD2 | Mixer mono passivo a 5 ingressi | 11 |
| MOD3 | DAC passivo R-2R a 5 bit | 12 |
| MOD4 | Mixer stereo a posizioni di pan fisse | 12 |
| MOD5 | XOR passivo + rettificatore semionda | 13 |
| MOD6 | Dual LPG / VC panner / diode clipper | 14-16 |

Cambio di configurazione

1. Spegni il sistema e scollega tutti i cavi.
2. Rimuovi tutti i jumper di configurazione della base e la scheda precedente.
3. Identifica la sigla della nuova MOD e il riferimento del suo connettore. Allinea le posizioni corrispondenti del 3 x 5; non spostare il connettore di una fila o di una colonna.
4. Se l’orientamento non è identificabile dalle serigrafie/documentazione della scheda, non forzare l’inserimento: verifica prima il riferimento della specifica MOD.
5. Per MOD6 imposta anche U10, U11, U13 e U12 come mostrato nelle pagine dedicate.

Non sovrapporre una scheda MOD ai ponti delle modalità base. Le posizioni di montaggio delle singole MOD non sono deducibili dal solo colore della PCB.

## MOD1 e MOD2: mixer passivi
Scheda opzionale richiesta. Nessun controllo di guadagno.

MOD1 - tre canali stereo

| JACK | FUNZIONE |
| 1 / 2 | Ingresso stereo 1: L / R su due cavi TS |
| A | Ingresso stereo 2 su TRS: tip L, ring R |
| 3 / 4 | Ingresso stereo 3: L / R su due cavi TS |
| B | Uscita stereo TRS: tip L, ring R |

Collega le sorgenti ai tre ingressi e porta B a un ingresso stereo ad alta impedenza o a un breakout TRS. In questa modalità 3 è L e 4 è R: è il circuito MOD1 a definire il percorso, non la mappa della modalità splitter della base.

MOD2 - cinque ingressi mono

| JACK | FUNZIONE |
| 1 | Ingresso mono 1 |
| 2 | Ingresso mono 2 |
| A | Ingresso mono 3 (TS) |
| 3 | Ingresso mono 4 |
| 4 | Ingresso mono 5 |
| B | Uscita mono (TS) |

La somma passiva attenua il segnale e dipende dalle impedenze collegate; non c’è makeup gain. Regola i livelli sulle sorgenti e recupera il guadagno a valle, se necessario. Queste schede non sono amplificatori per cuffie.

## MOD3: DAC / MOD4: panning
Due schede diverse, due usi distinti.

MOD3 - DAC R-2R a 5 bit

| JACK | PESO BINARIO |
| 1 | 1 (bit meno significativo) |
| 2 | 2 |
| A | 4 |
| 3 | 8 |
| 4 | 16 (bit più significativo) |
| B | Uscita del DAC nella patch descritta |

Invia fino a cinque gate con livelli alto/basso coerenti ai cinque ingressi; preleva da B una tensione a gradini. Le combinazioni dei cinque bit permettono 32 codici teorici. Valore assoluto e precisione dipendono da livelli, tolleranze e carico: non è una sorgente pitch calibrata.

MOD4 - cinque posizioni stereo fisse

| JACK | POSIZIONE |
| 1 | Tutto a sinistra |
| 2 | Intermedia sinistra |
| A | Centro |
| 3 | Intermedia destra |
| 4 | Tutto a destra |
| B | Uscita stereo TRS |

Inserisci sorgenti mono nei cinque jack di ingresso e porta B a un percorso stereo. Il pan è fissato dal jack scelto: non è una regolazione continua e non è controllato da CV.

## MOD5: XOR e rettificatore
Due sezioni sullo stesso preset opzionale.

| JACK | FUNZIONE |
| 1 | Ingresso XOR 1 |
| 2 | Ingresso XOR 2 |
| A | Uscita XOR |
| 3 | Ingresso rettificatore |
| 4 | Uscita semionda positiva |
| B | Uscita semionda negativa |

XOR: variazioni ritmiche

Collega due gate compatibili a 1 e 2 e preleva A. La funzione XOR ideale è alta quando uno solo dei due ingressi è alto, bassa quando entrambi sono uguali. Invia il risultato a un ingresso gate adatto e prova combinazioni di clock o pattern.

| INGRESSO 1 | INGRESSO 2 | XOR IDEALE |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Rettifica: separare le due semionde

Invia una forma d’onda bipolare al jack 3. Da 4 preleva la parte positiva; da B quella negativa. È una separazione delle polarità, non un’uscita a onda intera né una conversione automatica della semionda negativa in positiva.

Il circuito è passivo: diodi, ampiezza dei segnali e carico influenzano soglie e livelli. Non aspettarti livelli logici rigenerati o una rettifica ideale senza caduta di tensione.

## MOD6: dual LPG
Due percorsi controllati da tensione, con vactrol.

MOD6: U10 1-2, U11 2-3, U13 1-2, U12 1-2

| JACK | FUNZIONE |
| 1 | CV del canale LPG1 |
| 2 | Segnale audio del canale LPG1 |
| A | Uscita LPG1 |
| 3 | CV del canale LPG2 |
| 4 | Segnale audio del canale LPG2 |
| B | Uscita LPG2 |

Imposta i quattro jumper MOD6 come nello schema. Collega una sorgente audio a 2, la CV o l’inviluppo di controllo a 1 e porta A a un mixer/ingresso audio. Per il secondo canale usa 4 come segnale, 3 come controllo e B come uscita.

La sezione passiva a vactrol modifica il passaggio del segnale in funzione della CV. La risposta ha carattere dipendente dai componenti: attacco, decadimento e chiusura possono differire tra i due canali. Prova inviluppi o gate compatibili iniziando con livelli contenuti.

“LPG” è il nome della modalità nel progetto. Non sono specificati pendenza del filtro, banda, soglia CV o guadagno: il comportamento non va presentato come equivalente a un VCA lineare o a un filtro calibrato.

## MOD6: VC panner
Una CV comune, due ingressi e due uscite.

MOD6: U10 2-3, U11 1-2, U13 2-3, U12 1-2

| JACK | FUNZIONE |
| 1 | CV di controllo comune |
| 2 | Segnale in 1 |
| A | Uscita 1 |
| 3 | Non usato |
| 4 | Segnale in 2 |
| B | Uscita 2 |

Imposta i jumper come mostrato. Collega una CV al jack 1. Invia il segnale del primo percorso a 2 e quello del secondo a 4; preleva le uscite da A e B. Il jack 3 non è usato in questa modalità.

Patch per movimento stereo

Per distribuire lo stesso segnale ai due lati, duplicalo prima con un multiple o un’uscita già sdoppiata e porta le due copie a 2 e 4. Collega A al canale sinistro e B al destro di un mixer/registratore; modula 1 e ascolta il cambiamento del bilanciamento. La duplicazione iniziale richiede un percorso esterno: non è automatica all’interno della MOD6.

Il documento non specifica legge di pan, uniformità del livello o escursione CV. La risposta passiva a vactrol va regolata e valutata nella patch reale.

## MOD6: diode clipper
Un percorso passivo per modellare la forma d’onda.

MOD6: U10 2-3, U11 1-2, U13 1-2, U12 2-3

| JACK | FUNZIONE |
| 1 | Ingresso clipper |
| 2 | Non usato |
| A | Uscita clipper |
| 3 / 4 / B | Non usati |

Imposta U10, U11, U13 e U12 come nello schema. Collega un segnale audio a 1 e preleva A verso il tuo mixer o ingresso audio. Aumenta il livello della sorgente gradualmente e confronta il risultato con il segnale originale a volume di ascolto simile.

Il clipping a diodi modifica le parti della forma d’onda che superano la zona di conduzione dei componenti. Il cambiamento può essere poco evidente con segnali bassi e più marcato con segnali maggiori. Il circuito passivo non recupera il livello perso.

Non sono specificati soglia di clipping, simmetria o livello massimo ammesso. Non collegare uscite di potenza, alimentatori o tensioni sconosciute ai jack.

## Risoluzione dei problemi
Controlla prima cablaggio, cavo e modalità installata.

| SINTOMO | CONTROLLO |
| Manca un canale stereo | Usa TRS su A/B. Nello splitter: A L=1, A R=2, B L=4, B R=3. |
| Il mult unisce segnali inattesi | Rimuovi tutti i ponti e ricrea soltanto la configurazione scelta. Non inserire più sorgenti nello stesso gruppo. |
| Livello basso nel mixer | Attenuazione e dipendenza dal carico sono proprie della somma passiva. Recupera guadagno a valle. |
| CV pitch non precisa | Il carico di più ingressi può modificare la tensione. Usa distribuzione bufferizzata per tracking preciso. |
| MIDI non risponde | Verifica Type A/B, direzione In/Out e pin del modulo host. Il MIDI non viene convertito in CV. |
| Normale interrotto | Inserendo una spina in 2 o 4 il rispettivo contatto 2N/4N si apre: è il funzionamento previsto. |
| MOD6 non fa la funzione attesa | Controlla tutti e quattro i selettori nell’ordine U10, U11, U13, U12. |
| La MOD non entra / è disallineata | Spegni, rimuovi e verifica riferimento e allineamento del 3 x 5. Non forzare. |

Manutenzione

Maneggia il modulo dai bordi. Evita trazioni sui cavetti interni, liquidi e contatti tra la PCB e parti metalliche. Pulisci il pannello con un panno morbido asciutto; non spruzzare detergenti nei jack. Riconfigura jumper e schede soltanto a sistema spento.

## Riferimento rapido e fonti
Edizione aggiornata ai colori della versione fotografata.

| MODALITÀ BASE | PONTI POSTERIORI |
| Splitter / CV-Gate / adattatore MIDI | X1-Y1; X2-Y2; X3-Y3; X4-Y4 |
| Due mult 1 x 2 | X1-Y1; X4-Y4; Z1-Z2; Z3-Z4 |
| Un mult 1 x 5 | Come sopra + Y2-Y3 |
| Mult a 4 jack per breakout MIDI | Y2-Y3; Z1-Z2; Z3-Z4 |

Nel convertitore MIDI aggiungi sul frontale 1-3 e 2-4. Ogni riga della tabella è una configurazione alternativa, non un’aggiunta alle altre.

Dati fisici documentati

Formato nominale: 2 HP. Ingombro del frontale nel file di progetto: 10,16 x 128,50 mm. Connettori frontali da 3,5 mm; header posteriore 3 x 5, passo 2,54 mm. La profondità totale con scheda/cavi e il peso non sono specificati: verifica lo spazio nel case per la configurazione installata.

Riferimenti di questa edizione

Funzioni e schemi: “E103 FAUN manual.pdf”, 19 pagine. Mappa e continuità delle piste della base confrontate con Gerber_S2XMS_faun-BACK-PCB_2026-10-03.zip. Ingombro frontale: progetto V1.2 del 29 settembre 2026. Aspetto: foto IMG_3208-IMG_3224 e visuali fotorealistiche ricavate dalle foto attuali.

MIDI Type A/B e cablaggio host: Expert Sleepers, Tiny MIDI Breakout e manuale disting EX. Esempio MPC: Akai Professional, MPC One FAQ. Link consultati il 26 ottobre 2026:
[expert-sleepers.co.uk/tinymidibreakout.html](https://expert-sleepers.co.uk/tinymidibreakout.html)
[disting EX - user manual](https://expert-sleepers.co.uk/downloads/manuals/disting_EX_user_manual_1.24.pdf)
[Akai Professional - MPC One FAQ](https://support.akaipro.com/en/support/solutions/articles/69000816149-akai-pro-mpc-one-frequently-asked-questions)

Questa edizione documenta il progetto disponibile; la verifica sulle piste non sostituisce una prova sul prodotto assemblato. Le immagini illustrano l’aspetto, mentre pinout e jumper sono definiti dalle tabelle tecniche.
