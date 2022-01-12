---
title: Microsoft Teams Rooms portale
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Fornire una visualizzazione dell'integrità delle sale riunioni.
f1keywords: ''
ms.openlocfilehash: db8f6125bda335dfab2f9208fcfd8ab0f192e4e7
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767610"
---
# <a name="microsoft-managed-meeting-rooms-portal"></a>Portale delle sale riunioni gestite Microsoft

## <a name="overview"></a>Panoramica

Il portale delle sale riunioni gestite ("Portale sale") offre una visualizzazione dell'integrità delle sale riunioni. Una visualizzazione del cliente di questo portale è per la visibilità e il feedback degli utenti e per facilitare gli strumenti/procedure di monitoraggio esistenti.

L'ambito del monitoraggio è

- Visualizzazione degli eventi imprevisti
  - Problemi principali che interessano le chat room
  - Azioni necessarie per ripristinare lo stato integro delle chat room
  - Problemi oggetto di indagine da parte di Microsoft
- Visualizzazione dei Microsoft Teams room
  - Snapshot dello stato a Microsoft Teams Rooms (MTR) a livello di dispositivo
  - Cronologia e dettagli di base per ogni dispositivo

**Visualizzazione dei Microsoft Teams room**

- Snapshot dello stato a Microsoft Teams Rooms (MTR) a livello di dispositivo
- Cronologia e dettagli di base per ogni dispositivo

> [!Important]
> Rivedere [**Assegnare gli utenti al ruolo di**](enrolling-mtrp-managed-service.md#assign-users-to-the-managed-service-administrator-role) amministratore del servizio gestito e assicurarsi che l'accesso al portale sia limitato in base alle esigenze aziendali.

## <a name="terminology"></a>Terminologia

Ecco i termini usati di frequente nel portale.

|Termine |Significato |
| :- | :- |
|**Software di monitoraggio** |Agente di monitoraggio distribuito in ognuno dei dispositivi Microsoft Teams room. |
|**App** |Microsoft Teams app Room system (indipendentemente dal fatto che usi Skype for Business o Microsoft Teams come servizio di collaborazione. |
|**Sala/Dispositivo** |Il dispositivo Microsoft Teams sistema Room certificato. |
|**Non monitorato** | Il software di monitoraggio Microsoft distribuito come parte dei servizi gestiti non è in grado di connettersi ai servizi cloud. Non riceviamo dati di telemetria sul dispositivo. |
|<p>**Integro /** </p><p>**Non integro** </p>|Anomalie nel dispositivo/periferica. |
|**Soppresso** |Se è noto che un dispositivo è in manutenzione e i relativi avvisi devono essere ignorati, il dispositivo può essere eliminato deliberatamente. |
|**Onboarding** |Lo stato di un dispositivo della sala durante l'aggiunta della configurazione, ma non è pronto come sala regolarmente supportata. |
|**Evento imprevisto** |Un problema che interessa le esperienze di riunione degli utenti finali che devono intervenire. |
|**Configurazione non configurata correttamente** |La configurazione rilevata non è corretta/usata comunemente. |
|**Ticket di supporto** |Identificatore di rilevamento Microsoft interno che tiene traccia di tutte le comunicazioni/azioni relative a un evento imprevisto. |

## <a name="incidents-view"></a>Visualizzazione Eventi imprevisti

Questa visualizzazione è una panoramica della scheda Eventi imprevisti nel portale delle chat room gestite. Questa pagina è la home page predefinita del portale.

### <a name="top-level-summary"></a>Riepilogo di primo livello 
Il riepilogo di primo livello mostra a colpo d'occhio i problemi che interessano le chat room, le attività da eseguire e le attività che Microsoft sta eseguendo su di esse:

![Screenshot che mostra un riepilogo di primo livello dei problemi](../media/rooms-monitor-001new.png)

|# |Spiegazione |
| :- | :- |
|1 |Tipi di eventi imprevisti che interessano le chat room |
|2 |**AZIONE RICHIESTA:** elementi che richiedono l'intervento dell'utente per la risoluzione. |
|3 |**ASSEGNATO A MICROSOFT:** elementi attualmente esaminati dal personale Microsoft. |
|4 |**INDAGINE IN SOSPESO:** elementi nella coda che devono essere esaminati dal personale Microsoft. |

Gli eventi imprevisti si verificano in uno dei tre stati seguenti:

- **Azione necessaria:** assegnata all'utente per l'azione
- **Assegnato a Microsoft**: Assegnato a Microsoft per l'azione successiva
- **Indagine in sospeso:** in fase di indagine per i passaggi successivi

### <a name="reviewing-incidents"></a>Revisione degli eventi imprevisti

L'immagine seguente elenca tutti gli eventi imprevisti attualmente attivi nelle chat room. Quelli assegnati all'utente *sono in* alto: ecco cosa è necessario esaminare per i passaggi successivi. Inoltre, quelli assegnati a Microsoft o alle indagini in sospeso hanno dettagli che è possibile usare per intervenire.

Facendo clic su uno degli elementi con stato "**Azione richiesta**" vengono visualizzati altri dettagli sull'evento imprevisto.

## <a name="types-of-incidents"></a>Tipi di eventi imprevisti

Gli eventi imprevisti sono classificati in due tipi di gravità:

- **Importante:** gli eventi imprevisti che probabilmente causano problemi nelle riunioni e che devono essere prioritari.
- **Avviso:** eventi imprevisti che sono notifiche per pianificare azioni di manutenzione. Se queste non vengono prese in considerazione, è più probabile che nel corso del tempo si sia verificato un problema nelle sale. Gli avvisi hanno lo scopo di fornire il tempo necessario per pianificare e coordinare il supporto.

Un avviso potrebbe passare a "**Importante**" se non è stato visualizzato per un po'.

## <a name="health-status-of-device-and-incidents"></a>Stato di integrità del dispositivo e degli eventi imprevisti

Gli eventi imprevisti classificati **come "Importanti"** di gravità influiranno sullo stato di integrità di un dispositivo. Se a un dispositivo è associato almeno un evento di gravità **= "Importante",** viene classificato come **_dispositivo non integro._**

Gli eventi imprevisti classificati **come gravità "Avviso"** non influiscono sullo stato di integrità segnalato in un dispositivo. Tuttavia, se a un dispositivo sono associati eventi imprevisti a livello di avviso, verrà visualizzato con lo stato di integrità del dispositivo come indicato di seguito.

![Screenshot che mostra lo stato di integrità di una chat room](../media/rooms-monitor-004.jpg)

Di seguito sono riportati alcuni tipi di eventi imprevisti che potrebbero essere visualizzati e le spiegazioni per ogni tipo. Per ogni tipo, l'azione associata all'evento imprevisto sarà più specifica a seconda del problema.

**Tabella 1: Eventi imprevisti con gravità "Importante"**

|Tipo |Spiegazione |
| :- | :- |
|**Schermo** |Lo schermo connesso al dispositivo non sembra essere integro.|
|**Microfono conferenza, altoparlante conferenza** |I dispositivi audio (microfono/altoparlante) sembrano non configurati correttamente. |
|**Fotocamera** |La fotocamera collegata al dispositivo non sembra essere integra. |
|**Inserimento HDMI** |HdMI Ingest non è integro. |
|**Accesso (Exchange)** |Microsoft Teams'app Room accede alle informazioni del calendario da Exchange e qualsiasi problema con l'accesso riuscito verrà segnalato con un evento imprevisto di accesso. |
|**Accesso (Teams)** |Microsoft Teams'app Room accede al dispositivo e l'errore di accesso viene segnalato con questo evento imprevisto (se il cliente usa Teams). |
|**Accesso (Skype for Business)** |Microsoft Teams'app Room accede al dispositivo e l'errore di accesso verrà segnalato con questo evento imprevisto (se il cliente usa Skype for Business) |
|**Sensore di prossimità** |Microsoft Teams'app Sala invita i partecipanti a partecipare a una riunione se si trovano in prossimità. Gli errori di questa caratteristica verranno segnalati in questo incidente. |

**Tabella 2: Eventi imprevisti con gravità "Avviso"**

|Tipo |Spiegazione |
| :- | :- |
|**Versione dell'app** |La versione dell'Microsoft Teams room in esecuzione nel dispositivo non è aggiornata. Le versioni non aggiornate sono cause note dei problemi riscontrati dagli utenti. |
|**Versione del sistema operativo** |La versione del Windows operativo in esecuzione nella sala riunioni non è più consigliata. |
|**Rete** |Questo verrà rimosso come tipo di avviso a breve termine a causa del lavoro aggiuntivo necessario dopo la valutazione. |

## <a name="responding-to-incidents"></a>Risposta agli eventi imprevisti

Gli eventi imprevisti sono suddivisi in tre categorie: Azione richiesta, Indagine in sospeso o Assegnato a Microsoft.

### <a name="needs-action-incidents"></a>Eventi imprevisti di tipo "Azioni necessarie"

Gli eventi imprevisti con stato impostato su **"Azione richiesta"** vengono assegnati all'utente per eseguire un'azione correttiva.

Ogni evento imprevisto di questo tipo avrà un campo di azione con un'azione consigliata da Microsoft nel modo seguente:

![Screenshot che mostra l'azione consigliata per gli eventi imprevisti](../media/rooms-monitor-005.jpg)

- Se l'azione è stata eseguita, è possibile rispondere all'evento imprevisto con le note nella casella Rispondi, quindi scegliere "Assegna a Microsoft" prima di pubblicare.
- È anche possibile che la notifica non sia corretta in base alla revisione. In questo caso, inviare il feedback e assegnare di nuovo a Microsoft.
- Infine, se si vuole aggiungere un commento per fornire un contesto aggiuntivo per il proprio team o per il team Microsoft, pubblicare il messaggio senza attivare "Assegna a Microsoft".

>[!NOTE]
>L'azione correttiva può risolvere il problema e il monitoraggio delle chat room gestite cancella l'evento dall'elenco. Nella situazione precedente, potrebbe non essere possibile risolvere il problema e assegnarlo di nuovo a Microsoft. Questo problema verrà risolto in una versione futura.

### <a name="pending-investigation-incidents"></a>Eventi imprevisti di tipo "Inchiesta in sospeso"

Per gli incidenti in fase di indagine, il campo della descrizione contiene informazioni sull'incidente, le cause tipiche e le soluzioni che possono essere utili per risolvere determinati problemi in modo da poter agire senza indugio.

### <a name="assigned-to-microsoft-incidents"></a>Eventi imprevisti "Assegnati a Microsoft"

Per gli eventi imprevisti assegnati a Microsoft, il campo "Azione" conterrà brevi dettagli sui passaggi correttivi pianificati o progredati. Questi passaggi potrebbero richiedere la collaborazione con il team e la collaborazione estesa verrà eseguita tramite posta elettronica/chiamate in base alle esigenze. Una volta risolti, questi problemi scompariranno dal portale e in futuro ci sarà una cronologia per tenere traccia di questi incidenti e della loro risoluzione.

![Screenshot che mostra i passaggi correttivi ms](../media/rooms-monitor-006.jpg)

## <a name="rooms-view"></a>Visualizzazione Sale

Ogni dispositivo è un proxy per una sala e le relative periferiche connesse. Un dispositivo integro rappresenta una sala integra e un dispositivo non integro rappresenta una sala che probabilmente causa problemi durante le riunioni. Oltre alla visualizzazione Eventi imprevisti, il portale delle chat room gestite offre anche una panoramica dell'integrità della sala e consente di risolvere i dettagli dei dispositivi e di comprendere gli errori ripetuti con la cronologia degli eventi.

![Screenshot che mostra la panoramica dell'integrità di una sala](../media/rooms-monitor-007.jpg)

**Integro, Non integro, Disconnesso** Il riquadro superiore della visualizzazione Sale fornisce un rapido snapshot del numero di dispositivi in uno stato valido("Integro"), di quanti sono interessati da problemi ("Non integro"), di quanti non forniscono telemetria ("Disconnessi") e di quanti dispositivi vengono eliminati dall'avviso (come override). Le chat room vengono monitorate per l'integrità usando criteri ed euristici in evoluzione. L'obiettivo è riflettere la realtà dell'esperienza utente nella sala nel modo più accurato possibile e renderla utilizzabile.

**Sale sane/non integre**:

I dispositivi/periferiche che non hanno incidenti di gravità "Importante" soddisfano i criteri correnti per l'integrità sono contrassegnati come integri. Tuttavia, non implica che ci sia un'interruzione della sala per ogni dispositivo non integro nel portale. La parte relativa alla descrizione e all'azione dell'incidente contiene dettagli più specifici sul problema e sul potenziale impatto sull'esperienza utente.

**Dispositivo disconnesso:**

L'agente di monitoraggio Microsoft distribuito come parte del progetto pilota Managed Rooms viene disconnesso dai servizi cloud della chat room gestita. Non riceviamo dati di telemetria sulla chat room e non abbiamo lo stato di integrità più recente. Questo problema può verificarsi a causa di problemi di rete, modifiche ai criteri del firewall o se sono state apportate modifiche all'immagine del dispositivo.

## <a name="room-detail-status-and-changes"></a>Dettagli sala: stato e modifiche

**Dettagli sala: Stato** La scheda *Stato* dispositivo offre una visualizzazione consolidata dello stato di un dispositivo, tutti i problemi attivi per il dispositivo, le azioni necessarie per risolverli o che sono in corso. La scheda Stato contiene anche la suddivisione dei diversi componenti di integrità per il dispositivo nella *scheda Eventi imprevisti.* Se un dispositivo è disconnesso, i dettagli sullo stato non saranno disponibili.

![Screenshot che mostra la visualizzazione stato consolidato](../media/rooms-monitor-008.png)

**Mostra tutti i segnali:** Per visualizzare tutti i segnali contenuti in una categoria di segnali, abilitare l'interruttore Mostra tutti i segnali. Le frecce di espansione vengono visualizzate accanto alle intestazioni di categoria su cui è possibile fare clic per espandere la visualizzazione a accordi.

![Screenshot che mostra i segnali all'interno di una categoria](../media/rooms-monitor-009.png)

**Elimina/Riattiva ticket** Quando si registra una chat room, si indica che si vogliono ricevere notifiche per le modifiche nella telemetria della chat room. In alcuni casi, un dispositivo o una periferica specifica si trova in uno stato noto in cui non si vogliono generare ticket o notifiche. L'uso della funzionalità Elimina ticket consente di disattivare l'audio di qualsiasi notifica relativa a quel particolare segnale. Quando si è pronti per il monitoraggio e la notifica del segnale, è sufficiente riattivare il singolo segnale.

![Screenshot che mostra i ticket soppressi della chat room](../media/rooms-monitor-010.png)

**Espansione delle categorie di biglietti attivi** In ogni categoria di ticket, tutti i ticket risolti attivi o più recenti verranno visualizzati insieme alla gravità e alla data dell'ultimo aggiornamento del ticket. Facendo clic sulla freccia di espansione, tutti i ticket verranno visualizzati con un collegamento attivo alle informazioni sul biglietto.

Espansione categoria biglietto attivo: in ogni categoria di ticket, tutti i ticket risolti attivi o più recenti verranno visualizzati insieme alla gravità e alla data dell'ultimo aggiornamento del ticket. Facendo clic sulla freccia di espansione, tutti i ticket verranno visualizzati con un collegamento attivo alle informazioni sul biglietto.

![Screenshot che mostra la categoria di ticket risolta](../media/rooms-monitor-011.png)

## <a name="active-ticket-overview"></a>Biglietto attivo: panoramica

Ogni evento imprevisto creato identifica il problema rilevato e l'azione correttiva da eseguire per ripristinare lo stato integro della chat room. Il ticket generato trasmetterà una panoramica degli eventi imprevisti con tutti i messaggi generati dall'intelligenza artificiale dei servizi gestiti e dal team di progettazione dei servizi Microsoft che sta analizzando il problema. Verranno elencati tutti gli allegati raccolti per la risoluzione dei problemi relativi agli incidenti. La scheda Cronologia contiene le date in cui sono stati identificati i problemi.

![Screenshot che mostra la panoramica dei ticket attivi](../media/rooms-monitor-012.png)

Ticket attivo: messaggi L'interfaccia utente dei messaggi è lo strumento di comunicazione principale per interagire con i tecnici del servizio Microsoft che lavorano per risolvere il problema identificato. È importante confermare le comunicazioni di Microsoft per garantire che microsoft fornisca il miglior servizio possibile. Se sono state intraprese le azioni consigliate, rispondere a questo evento con le note nella casella Rispondi e assegnare di nuovo a Microsoft facendo clic su "Assegna a Microsoft" prima di pubblicare.
È anche possibile che la notifica non sia corretta in base alla revisione. In questo caso, inviare il feedback e assegnare di nuovo a Microsoft.
Infine, se si vuole aggiungere un commento per fornire un contesto aggiuntivo per il proprio team o per il team Microsoft, è sufficiente pubblicare il messaggio senza attivare "Assegna a Microsoft

![Screenshot che mostra i messaggi dei ticket attivi](../media/rooms-monitor-013.png)


Biglietto attivo: allegati In alcuni casi i tecnici dei servizi Microsoft hanno bisogno di informazioni aggiuntive per aumentare l'indagine sul problema. La scheda degli allegati offre la possibilità di caricare immagini, video o log richiesti.

![Screenshot che mostra gli allegati di ticket attivi](../media/rooms-monitor-014.png)

Biglietto attivo: Cronologia Ogni segnale della sala ha un solo numero di biglietto assegnato appositamente. Un dispositivo o una periferica della sala persiste in una chat room e può avere problemi nel tempo. Mantenendo queste informazioni in base a un ID ticket univoco specifico, tutte le informazioni storiche vengono mantenute e possono essere analizzate per i modelli di comportamento. L'interfaccia utente Cronologia offre una visualizzazione di tutte le azioni dei ticket create e risolte per questo segnale.

![Screenshot che mostra la cronologia dei ticket attivi](../media/rooms-monitor-015.png)

Domande frequenti In che modo i ticket dinamici influiscono su di me e sulle operazioni delle mie sale?  
I clienti potranno vedere la creazione di ticket e correzioni più intelligenti che si espandono oltre un semplice ticket di segnale binario. Ad esempio, possono essere presenti fino a tre schermi in un Sala riunioni (Display 1, Display 2 & display del touch panel MTR). Tuttavia, il segnale di visualizzazione 1 (uno) è integro o non integro. Con i nuovi ticket dinamici, ora è possibile generare ticket univoci per ogni segnale di visualizzazione.
