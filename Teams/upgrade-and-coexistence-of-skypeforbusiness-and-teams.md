---
title: Aggiornamento di Microsoft Teams da Skype for business | Modalità, coesistenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Informazioni dettagliate sulle opzioni e le modalità di coesistenza di Skype for business e Microsoft teams e l'aggiornamento dei viaggi ai team da Skype for business con scenari di esempio.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d662dfd98aa4706d32a7e9ba3bec06d5e32ae975
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "36185233"
---
![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione] (media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Scegliere il viaggio di aggiornamento da Skype for business a teams

Come cliente esistente di Skype for business, la transizione completa ai team può richiedere del tempo. Puoi tuttavia iniziare a realizzare il valore dei teams oggi, consentendo agli utenti di usare teams insieme a Skype for business. Poiché esistono alcune funzionalità sovrapposte tra le due app, è consigliabile esaminare le modalità di coesistenza e di aggiornamento disponibili per determinare il percorso appropriato per l'organizzazione. Ad esempio, è possibile scegliere di abilitare tutti i carichi di lavoro su entrambe le soluzioni senza interoperabilità. In alternativa, potresti decidere di gestire l'esperienza utente, introducendo gradualmente le funzionalità dei team o puntando su gruppi di utenti per le funzionalità di selezione, finché l'organizzazione non è pronta per aggiornare tutti i team. Usa il risultato del tuo pilota per valutare il viaggio di aggiornamento giusto per l'organizzazione.

> [!IMPORTANT]
> Skype for business online verrà ritirato il 31 luglio 2021, dopodiché non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams.

In questo articolo vengono illustrate le varie modalità che consentono di gestire quali modalità in Skype for business e teams sono disponibili per gli utenti. Come per qualsiasi distribuzione, ti consigliamo vivamente di [pilotare il piano previsto](pilot-essentials.md) con un gruppo selezionato di utenti prima di aggiornare l'organizzazione a teams. Tenere presente che l'introduzione di una nuova tecnologia può essere di disturbo per gli utenti. Richiedere tempo per valutare la disponibilità degli utenti e implementare un piano di comunicazione e formazione prima di implementare una delle modalità descritte in questo documento.

> [!TIP]
> Unisciti a noi per laboratori interattivi e dinamici in cui condivideremo le linee guida, le procedure consigliate e le risorse progettate per avviare la pianificazione e l'implementazione dell'aggiornamento.
>
>Prima di tutto, partecipa al piano della sessione di [aggiornamento](https://aka.ms/SkypeToTeamsPlanning) per iniziare.


## <a name="upgrade-journey-building-blocks"></a>Aggiornare i blocchi predefiniti di viaggio

Per preparare formalmente l'organizzazione per il viaggio in teams, è necessario avviare la pianificazione per gli scenari di aggiornamento che consentiranno alla tua organizzazione di accettare completamente i team come unica soluzione di comunicazione e collaborazione.

Per aiutare a guidare il processo decisionale, familiarizzare con le varie modalità, i concetti e la terminologia pertinenti per l'aggiornamento da Skype for business a teams. Per altre informazioni, vedere coesistenza e interoperabilità di [Microsoft teams e Skype for business](https://aka.ms/SkypeToTeams-Coexist)

Quando alcuni utenti sono pronti a usare solo team per le comunicazioni quotidiane e le esigenze di collaborazione, è possibile iniziare a eseguire l'aggiornamento di questi utenti ai team abilitando la modalità **solo teams** .

Se non è possibile che l'intera organizzazione venga spostata in teams, è possibile iniziare pilotando teams insieme a Skype for business in modalità di coesistenza per le **isole** . Le modalità di coesistenza aggiuntive (ad esempio **Skype for business con teams Collaboration** e **Skype for business con la collaborazione e le riunioni**di Teams) diventano progressivamente disponibili nei prossimi mesi, ma è anche possibile iniziare completamente l'adozione di teams come soluzione di collaborazione di gruppo prima di tutto mantenendo Skype for business come soluzione di Unified Communications dell'organizzazione. Questo è il percorso consigliato da Microsoft per i clienti che usano Skype for Business Server (locale o ibrido) e i clienti con una complessità significativa la cui traiettoria per i team includerà un lungo periodo di coesistenza.

![Screenshot dell'aggiornamento dei blocchi predefiniti da Skype for business a teams] (media/upgrade_journeys_building_block.png "Screenshot dell'aggiornamento dei blocchi predefiniti da Skype for business a teams, costituito da Skype for business con la&ndash;modalità di collaborazione in teams, Skype for business con la modalità di collaborazione e riunione in teams, modalità Islands, modalità solo teams e Skype for Modalità&ndash;solo business.")

Nella tabella seguente vengono confrontate le modalità di coesistenza e aggiornamento.

|Modalità |Situazione |Uso consigliato |Vantaggi |Aspetti |
|---|---|---|---|---|
|Isole |Distribuzione Skype for business più piccola o più semplice<br><br>Capacità e disponibilità a gestire una complessità a breve termine per spostarsi in team più rapidamente |Accedere all'esperienza team completa il più rapidamente possibile<br><br>Condurre un proof of Concept (PoC) di Teams<br><br>Percorso di aggiornamento consigliato per le organizzazioni che hanno adottato Skype for business online |Semplice da usare<br><br>Le squadre più ricche hanno esperienza in anticipo per tutte le funzionalità |Richiede una buona comunicazione degli utenti per evitare confusione e guidare l'utilizzo verso i team<br><br>Exit Strategy richiede agli utenti di avere pienamente adottato teams prima di iniziare l'aggiornamento alla fase solo Teams<br><br>Nessuna interoperabilità per gli utenti in modalità Isole; Inoltre nessuna federazione da teams quando l'account Skype for business dell'utente viene ospitato in locale|
|Collaborazione tra Skype for business e teams |Distribuzione di Skype for business con requisiti non ancora soddisfatti da Teams (ad esempio, conformità avanzata)<br><br>Necessità e/o impegno a lungo termine per Skype for business|Avviare rapidamente l'adozione di Team, concentrandosi innanzitutto sulla collaborazione di gruppo<br><br>Vuoi conservare tutti i carichi di lavoro delle comunicazioni unificate in Skype for business per ora<br><br>Uso consigliato come punto di partenza per l'organizzazione che avvia il viaggio da un locale (o ibrido) Skype for business|Nessuna funzionalità sovrapposta tra teams e Skype for business<br><br>La chat di messaggistica istantanea e la pianificazione delle riunioni si trovano in Skype for business (legato alla chiamata)<br><br>Interoperabilità con gli utenti solo in teams|
|Skype for business con la collaborazione e le riunioni di Teams |Distribuzione di Skype for business con un uso significativo della voce aziendale e dei requisiti che non sono ancora stati raggiunti da teams Calling<br><br>Necessità e/o impegno a lungo termine per Skype for business<br><br>Potrebbe essere l'uso di un servizio di riunione di terze parti|Avviare rapidamente l'adozione di teams, superando la collaborazione di gruppo<br><br>Migliorare l'esperienza delle riunioni degli utenti<br><br>Uso consigliato per le organizzazioni locali che vogliono sfruttare le riunioni di teams prima di essere pronte per l'aggiornamento completo (in genere a causa di Enterprise Voice locale). |Nessuna funzionalità sovrapposta<br><br>Riunioni superiori in teams. Funzionalità roadmap, UX e Cross Platform, qualità e affidabilità<br><br>Esperienze "Better Together" tra Skype for business e teams<br><br>Utenti di interoperabilità solo in teams.|La messaggistica istantanea e la chat si trovano in Skype for business (legato alla chiamata)|
|Solo Teams |I team sono solo la destinazione finale per tutti gli utenti, alla fine.<br><br>Alcuni utenti devono rimanere in Skype for business<br><br>Stai aggiornando gli utenti di Skype for business online a teams mantenendo gli utenti locali di Skype for business su Skype for Business Server<br><br>Potresti avere già distribuito utenti in modalità isole e sei pronto per ritirare Skype for business per gruppi di utenti |Ridurre i costi variabili in Skype for business (operazioni server locali, contratto di outsourcing e così via)<br><br>Accedere all'esperienza completa di teams il più rapidamente possibile, almeno per alcuni utenti|Limita la confusione degli utenti fornendo un solo client per lavorare con l'interoperabilità con gli utenti solo in Skype for business, Skype for business con Collaboration teams, Skype for business con la collaborazione e le riunioni di Teams|L'interoperabilità supporta solo la chat di base e le chiamate tra Skype for business e teams e gli scenari di interoperabilità per la condivisione desktop e la chat e le chiamate a più parti|
|Solo Skype for business |Alcuni utenti devono rimanere in Skype for business<br><br>|Limita la confusione degli utenti fornendo un solo client con cui lavorare<br><br>L'utente può comunque partecipare a riunioni di team a cui sono invitati|Continuare a soddisfare i requisiti aziendali che attualmente possono essere soddisfatti solo da Skype for business<br><br>Interoperabilità con gli utenti solo in teams|L'interoperabilità supporta solo la chat di base e le chiamate tra Skype for business e teams e gli scenari di interoperabilità per la condivisione desktop e la chat e le chiamate a più parti|

> [!TIP]
> Per identificare la modalità di aggiornamento consigliata in base alle funzionalità che si vogliono abilitare in teams mentre Skype for business è ancora in uso, sfruttare la [procedura guidata di aggiornamento di Skype to teams](https://aka.ms/SkypeToTeamsWizard).

## <a name="upgrade-journeys"></a>Aggiornare i viaggi

È possibile adottare più approcci per l'aggiornamento da Skype for business, online o locale, a teams:

- In un viaggio di aggiornamento diretto devi prima distribuire teams insieme a Skype for business in **Islands** mode come parte della valutazione e dell'adozione iniziale e quindi aggiornare gli utenti alla modalità **solo teams** con l'obiettivo di ritirare rapidamente Skype for business dal ambiente per tutti gli utenti dell'organizzazione. Questo è il viaggio consigliato per i clienti Skype business online, a meno che non si preoccupi che i loro utenti vengano confusi con due strumenti per eseguire la stessa azione (chat, chiamata, pianificazione delle riunioni).
- Un viaggio di aggiornamento graduale offre una specifica modalità di coesistenza e aggiornamento a un gruppo specifico di utenti (detto anche *coorte*), a seconda dei requisiti di comunicazione e collaborazione. Nel corso del tempo, l'intera organizzazione può confluire nell'uso di teams only e infine sostituire Skype for business. Tuttavia, se l'organizzazione ha motivi commerciali interessanti per evitare Skype for business, ad esempio una dipendenza da una soluzione basata su Unified Communications Managed API (UCMA), che si integra con le applicazioni line-of-business o da una soluzione di Wall Ethical attualmente disponibile solo per Skype for business o per una distribuzione VoIP aziendale complessa che deve richiedere tempo per l'aggiornamento a **Teams only**, è possibile aggiornare una parte degli utenti alla modalità **solo teams** mantenendo gli utenti di Skype for business in una delle modalità di coesistenza per una parte del popolamento degli utenti. Il percorso di aggiornamento graduale è l'approccio consigliato per i clienti locali (e ibridi) che iniziano con Skype for business con la modalità di coesistenza di teams e si spostano da lì alla modalità solo teams quando i requisiti per gli utenti si incontrano (possibilmente tramite il Skype for business con la modalità di coesistenza di teams e meetings.

> [!IMPORTANT]
> Per entrambi i tipi di viaggio di aggiornamento, se l'organizzazione è attualmente una distribuzione locale di Skype for business, è necessario iniziare a pianificare l'implementazione di Skype for business Hybrid prima di aggiornare gli utenti alla modalità **solo teams** . Questo aiuterà anche a facilitare l'interoperabilità con i team.

> [!NOTE]
> La modalità **solo teams** richiede che gli utenti che fanno parte di coorti siano ospitati in Skype for business online e che sia necessaria una relazione ibrida tra la distribuzione locale di Skype for business e il tenant di Skype for business online per facilitare l' interoperabilità tra Skype for business e teams. Il passaggio a Skype for business online deve essere completato per gli utenti che fanno parte delle coorti prima di essere aggiornati alla modalità **solo teams** . Skype for Business Server 2019 e Skype for Business Server 2015 con CU8 Update possono semplificare la meccanica dell'aggiornamento degli utenti locali ai team gestendo la migrazione a Skype for business online e aggiornando gli utenti alla modalità **solo teams** in un unico passaggio .

### <a name="direct-upgrade-journey"></a>Percorso di aggiornamento diretto

Il percorso di aggiornamento diretto è illustrato nel diagramma seguente.

![Screenshot del percorso di aggiornamento diretto] (media/upgrade_journey_direct_upgrade.png "Screenshot del percorso di aggiornamento diretto. Tutti gli utenti usano inizialmente teams in modalità isole, quindi transizione alla modalità solo teams, con lo stato finale dell'intera organizzazione aggiornata a teams.")

I team vengono distribuiti a tutti gli utenti dell'organizzazione e configurati in modalità **isole** . Quando l'organizzazione determina che i team sono pronti a soddisfare tutte le esigenze di comunicazione e collaborazione, avvisa gli utenti e aggiornali alla modalità **solo teams** . A questo punto, Skype for business può essere ritirato dall'ambiente.

### <a name="gradual-upgrade-journey"></a>Percorso di aggiornamento graduale

Un esempio di percorso di aggiornamento graduale è illustrato nel diagramma seguente.

![Esempio illustrato del percorso di aggiornamento graduale] (media/upgrade_journey_gradual_upgrade.png "Nel percorso di aggiornamento graduale, le coorti degli utenti usano inizialmente teams in modalità Islands per la valutazione e quindi in una varietà di modalità di aggiornamento per l'adozione iniziale, affiancate da Skype for business. Alcune coorti possono passare alla modalità solo teams, mentre un gruppo di utenti rimane con Skype for business con la modalità di collaborazione e riunione teams.")

Teams è distribuito nell'organizzazione in modalità **Islands** per la valutazione e quindi passa a diverse modalità di coesistenza e aggiornamento per diversi gruppi di utenti. Ad esempio, un gruppo di utenti può essere abilitato per la modalità **isole** , un altro abilitato per **Skype for business con la modalità di collaborazione e riunione in teams** , mentre un terzo gruppo di utenti potrebbe inizialmente essere abilitato per **Skype for business con teams modalità di sola collaborazione** .

Nel tempo, i gruppi di utenti possono essere aggiornati alla modalità **solo teams** , seguiti dal resto dell'organizzazione. L'intera organizzazione sarà quindi pronta a ritirare Skype for business e a usare solo team per comunicazioni e collaborazione oppure, se i requisiti aziendali impongono che Skype for business venga mantenuto per un gruppo specifico, la maggior parte degli utenti del l'organizzazione può usare solo teams. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto decisionale</td><td><ul> Quale viaggio di aggiornamento è adatto ai requisiti aziendali dell'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Passaggio successivo</td><td><ul> L'identificazione del modello di distribuzione corrente, l'uso di scenari di casi e le considerazioni chiave per l'organizzazione informano il viaggio ai team più adatti per l'organizzazione.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto decisionale</td><td><ul> Quale scenario di aggiornamento è applicabile all'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul> Decidi la sequenza temporale del viaggio di aggiornamento dell'organizzazione in base a messaggi, riunioni e requisiti aziendali per le chiamate.<br><br> Decidere il lavoro aggiuntivo necessario per completare il viaggio di aggiornamento.<br><br></ul></td></tr>
</table>

Dopo aver scelto il viaggio di aggiornamento migliore per l'organizzazione, [eseguire l'aggiornamento a teams](https://aka.ms/SkypeToTeams-Upgrade).
