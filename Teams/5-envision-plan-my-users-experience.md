---
title: Pianificare l'esperienza degli utenti di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scegliere le app client di Teams, pianificare la qualità dell'endpoint, ottenere consigli per la distribuzione Wi-Fi endpoint e la scelta di dispositivi audio.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad827244baaacde8ee5c7166590c81347c8eea5b
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610021"
---
# <a name="plan-my-users-experience"></a>Pianificare l'esperienza degli utenti

Questo articolo offre una panoramica dei requisiti per identificare correttamente gli elementi della distribuzione dei servizi vocali cloud che influiscono direttamente sull'esperienza degli utenti. La preparazione di questi elementi prima della distribuzione aumenta la possibilità di offrire agli utenti un'esperienza affidabile e di alta qualità. 

## <a name="client-deployment"></a>Distribuzione client

Microsoft Teams ha client disponibili per il Web, il desktop (Windows e Mac) e per dispositivi mobili (Android e iOS). Per altri dettagli sulla modalità di installazione dei client desktop (Windows e Mac) e per dispositivi mobili, vedere Ottenere [client per Microsoft Teams.](https://docs.microsoft.com/microsoftteams/get-clients)

## <a name="client-updates"></a>Aggiornamenti del client

Uno dei vantaggi principali di Teams è che il cliente viene mantenuto aggiornato automaticamente. I client nel PC e nel Mac vengono aggiornati usando un processo in background che verifica la presenza di nuove build e scarica il nuovo client quando l'app è inattiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Pianificare la qualità dell'endpoint

Come si può vedere dal diagramma seguente, gli endpoint sono un elemento predefinito importante per offrire un'esperienza di qualità agli utenti.

![Diagramma che descrive i tre componenti della qualità](media/plan-my-users-experience-image1.png "Diagramma che descrive i tre componenti della qualità e come la gestione dei servizi si sovrappone a tutti e tre i componenti. Con lo stato attivo sugli endpoint.")

Gli endpoint di Teams possono essere eseguiti su molti dispositivi, inclusi PC, Mac, tablet e dispositivi mobili. Parte dell'esperienza non comprende solo il dispositivo, ma anche il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono/altoparlante incorporato del dispositivo, gli auricolari o un auricolare ottimizzato. L'uso di un auricolare ottimizzato può arricchire l'esperienza utente complessiva.

Le seguenti indicazioni sulla pianificazione degli endpoint aiuteranno a garantire all'organizzazione un'esperienza di onboarding con Teams di successo.

## <a name="endpoint-capability"></a>Funzionalità endpoint

La prima parte della pianificazione è garantire che tutti i PC e gli altri dispositivi dell'organizzazione possano eseguire Teams. Questo implica non solo l'aspetto dei requisiti hardware, ma anche la comprensione delle altre attività del PC in background. Molte organizzazioni eseguono altro software, inclusi i sistemi di rilevamento delle intrusioni e il software antimalware, che possono influire sulle prestazioni di base di un dispositivo.

Per informazioni sui requisiti software per i client di Teams su ogni piattaforma (web, desktop e mobile), vedere Ottenere [i client per Microsoft Teams.](https://docs.microsoft.com/microsoftteams/get-clients)

## <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente.
I firewall sul lato client possono influire sulla qualità delle chiamate, oltre a impedire che venga stabilita una chiamata. Configurare le esclusioni appropriate nel firewall client in base alle informazioni in URL e intervalli di indirizzi IP per [Microsoft 365 o Office 365.](https://aka.ms/o365ips) Il fornitore di terze parti avrà indicazioni specifiche su come creare le esclusioni.

>[!NOTE]
> Microsoft Teams aggiornerà automaticamente Windows Firewall con una configurazione del firewall appropriata.

## <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi suggerimenti per gli endpoint

Ci vuole una pianificazione significativa per distribuire una rete Wi-Fi ottimizzata per supportare i carichi di lavoro in tempo reale in Microsoft Teams. Le sezioni seguenti forniscono alcune indicazioni generali che consentono di evitare problemi comuni durante la pianificazione degli endpoint.

### <a name="wi-fi-drivers"></a>Wi-Fi driver

Alcuni Wi-Fi driver possono essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressivi tra i punti di accesso, causando una scarsa qualità della chiamata.
Non si tratta di un'occorrenza comune, ma è importante assicurarsi che i driver Wi-Fi nel PC siano stati aggiornati e testati prima della distribuzione.

### <a name="wi-fi-bands"></a>Wi-Fi bande

Attualmente vengono utilizzati principalmente due tipi di bande di dispositivi Wi-Fi, 2,4 GHz e 5,0 GHz. Se la tua organizzazione fornisce entrambe le bande, devi configurare le impostazioni del driver in modo da preferire la banda da 5,0 GHz. Questa banda è molto più spessa in termini di velocità effettiva ed è meno interessata dalle interferenze osservate nella banda da 2,4 GHz.
Questa consiglio presuppone che la banda di rete da 5,0 GHz sia stata ottimizzata correttamente.

### <a name="wi-fi-radio-type"></a>Wi-Fi di opzione

Pianificare i dispositivi che supportano i tipi di Wi-Fi radio più nuovi. È possibile ottenere prestazioni di Wi-Fi se si usa la versione 802.11ac o versioni più nuove nei dispositivi di cui viene eseguito il provisioning.

### <a name="wireless-avoidance"></a>Evitare wireless

Alcune organizzazioni preferiscono evitare di Wi-Fi del tutto. A volte queste indicazioni vengono fornite tramite consigli agli utenti per connettersi direttamente a una rete cablata. In alcuni casi, l'ordine di associazione della rete potrebbe avere la connessione wireless preferita e continuare a usare tale connessione anche se il PC è connesso alla connessione cablata. Per evitare questo comportamento indesiderato, configurare l'ordine di associazione per evitare questo scenario.

### <a name="80211-power-save-protocol"></a>Protocollo Power Save 802.11

Se l'organizzazione usa punti di accesso wireless o router che non supportano il protocollo Power Save 802.11, potrebbero verificarsi chiamate interrotta o qualità scarsa delle chiamate in Microsoft Teams in esecuzione su dispositivi Windows. Se non è possibile aggiornare il punto di accesso wireless o i router, è consigliabile aggiornare le impostazioni di Power Plan di Windows nei dispositivi con alimentazione a batteria. Altre informazioni dettagliate e istruzioni di configurazione sono disponibili nell'articolo [del supporto tecnico seguente.](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Quali client di Teams verranno distribuiti nell'organizzazione?</li><li>Come si distribuiranno inizialmente i client di Teams agli utenti?</li><li>Chi è responsabile della valutazione di endpoint e dispositivi per convalidare che soddisfino i requisiti di Teams per un'esperienza di qualità?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il processo che verrà seguito per distribuire i client di Teams.</li><li>Valutare gli endpoint e i dispositivi ed eseguire e correggere i problemi necessari.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivi per Teams

Microsoft Teams può essere usato per le riunioni o come sistema telefonico. Quando si usano queste funzionalità, il dispositivo di interfaccia usato per Teams svolge un ruolo importante nell'esperienza utente.

L'uso di un altoparlante e un microfono incorporati per PC potrebbero sembrare accettabili per l'utente che dispone di tale configurazione. In genere, però, questi dispositivi non sono ottimizzati per l'eliminazione del rumore e qualsiasi tipo di rumore di fondo può avere un impatto a valle sugli altri utenti durante la chiamata. L'uso di dispositivi ottimizzati per questi scenari garantirà un'esperienza di alta qualità.

Ogni dispositivo deve soddisfare le esigenze degli utenti. Sarà necessario personalizzare dispositivi come le cuffie per i diversi utenti tipo e casi d'uso dell'organizzazione.
Nell'ambito del processo di pianificazione deve essere completata un'esercitazione sulla mappatura tra utenti tipo.

Dopo aver selezionato i dispositivi, includerli nel piano di test pilota per la convalida finale. Sfruttare i sondaggi durante il progetto pilota per raccogliere feedback e assicurare che la strategia del dispositivo sia ottimale.

> [!NOTE]
> Al momento, è consigliabile utilizzare dispositivi audio certificati tramite il programma di certificazione Skype for Business. Per trovare i dispositivi certificati in questo programma, vedere i dispositivi [Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices) e i dispositivi audio e [video USB.](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere la strategia complessiva dei dispositivi dell'organizzazione per le esperienze utente e sala riunioni.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Completa un'esercitazione sulla mappatura tra utenti tipo per dispositivo per l'organizzazione.</li><li>Documentare il processo per ottenere i dispositivi per gli utenti e le sale riunioni.</li><li>Documentare il processo di distribuzione e configurazione dei dispositivi per utenti e sale riunioni.</li><li>Procurarsi i dispositivi iniziali per iniziare la distribuzione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
