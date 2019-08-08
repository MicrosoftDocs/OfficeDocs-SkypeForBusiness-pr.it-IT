---
title: Pianificare l'esperienza degli utenti in Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scegliere le app client teams, pianificare la qualità degli endpoint, ottenere suggerimenti per la distribuzione di endpoint Wi-Fi e la scelta di dispositivi audio.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 688b1d05acb882b08128fa144f28bd8e682d57fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235508"
---
# <a name="plan-my-users-experience"></a>Pianificare l'esperienza degli utenti

Questo articolo offre una panoramica dei requisiti per identificare correttamente gli elementi della distribuzione dei servizi cloud Voice che influiscono direttamente sull'esperienza degli utenti. Preparando questi elementi prima della distribuzione, potrai aumentare le tue possibilità di offrire un'esperienza affidabile e di alta qualità per gli utenti. 

## <a name="client-deployment"></a>Distribuzione client

Microsoft teams è disponibile per i client Web, desktop (Windows e Mac) e per dispositivi mobili (Android e iOS). Per informazioni dettagliate su come sono installati i client desktop (Windows e Mac) e i dispositivi mobili, vedere [ottenere client per Microsoft teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Aggiornamenti client

Uno dei vantaggi principali di teams è che il client è mantenuto aggiornato automaticamente. I client del PC e del Mac vengono aggiornati usando un processo in background che verifica la ricerca di nuove compilazioni e Scarica il nuovo client quando l'app è inattiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Pianificare la qualità di endpoint

Come si può vedere dal diagramma seguente, gli endpoint sono un blocco predefinito importante per offrire un'esperienza di qualità per gli utenti.

![Diagramma che descrive i tre componenti della qualità] (media/plan-my-users-experience-image1.png "Diagramma che descrive i tre componenti della qualità e in che modo la gestione dei servizi si sovrappone a tutti e tre i componenti. Con lo stato attivo sugli endpoint.")

I team endpoint possono essere eseguiti in molti dispositivi, tra cui PC, Mac, tablet e dispositivi mobili. Parte dell'esperienza non include solo il dispositivo, ma anche il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono/altoparlante incorporato del dispositivo, gli auricolari o un auricolare ottimizzato. L'uso di un auricolare ottimizzato può arricchire l'esperienza utente complessiva.

Le linee guida seguenti per la pianificazione degli endpoint consentiranno di verificare che l'organizzazione abbia un'esperienza di onboarding efficace con i team.

## <a name="endpoint-capability"></a>Funzionalità endpoint

La prima parte della pianificazione consiste nel garantire che tutti i PC e altri dispositivi dell'organizzazione possano eseguire teams. Questo implica non solo esaminare i requisiti hardware, ma anche capire cos'altro sta facendo il PC in background. Molte organizzazioni eseguono altri software, inclusi i sistemi di rilevamento delle intrusioni e il software antimalware, che possono influire sulle prestazioni di base di un dispositivo.

Per informazioni sui requisiti software per i client di team in ogni piattaforma (Web, desktop e mobile), vedere [ottenere client per Microsoft teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente.
I firewall lato client possono influire sulla qualità delle chiamate oltre a impedire la creazione di una chiamata. Configurare le esclusioni appropriate nel firewall client in base alle informazioni contenute negli [URL e negli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips). Il fornitore di terze parti avrà indicazioni specifiche su come creare le esclusioni.

>[!NOTE]
> Microsoft teams aggiornerà automaticamente Windows Firewall con una configurazione appropriata del firewall.

## <a name="wi-fi-recommendations-for-endpoints"></a>Raccomandazioni Wi-Fi per gli endpoint

È necessario pianificare in modo significativo la distribuzione di una rete Wi-Fi ottimizzata per supportare i carichi di lavoro in tempo reale in Microsoft teams. Nelle sezioni seguenti sono disponibili indicazioni generali che consentono di evitare problemi comuni quando si pianificano gli endpoint.

### <a name="wi-fi-drivers"></a>Driver Wi-Fi

Alcuni driver Wi-Fi possono essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressivi tra i punti di accesso, causando una scarsa qualità delle chiamate.
Non si tratta di un'occorrenza comune, ma è importante assicurarsi che i driver Wi-Fi nel PC siano stati aggiornati e testati prima della distribuzione.

### <a name="wi-fi-bands"></a>Bande Wi-Fi

Ci sono principalmente due tipi di bande usate oggi in apparecchiature Wi-Fi, 2,4 GHz e 5,0 GHz. Se l'organizzazione fornisce entrambe le bande, è consigliabile configurare le impostazioni del driver per preferire la banda di 5,0 GHz. Questa banda è molto più densa in termini di velocità effettiva ed è meno influenzata dall'interferenza riscontrata nella banda di 2,4 GHz.
Questa raccomandazione presuppone che sia stata ottimizzata correttamente la banda di rete di 5,0 GHz.

### <a name="wi-fi-radio-type"></a>Tipo di radio Wi-Fi

Pianificare i dispositivi che supportano i più recenti tipi di radio Wi-Fi. È possibile ottenere ottime prestazioni Wi-Fi se si sfruttano 802.11 AC o versioni successive sui dispositivi che si provisionano.

### <a name="wireless-avoidance"></a>Evitamento wireless

Alcune organizzazioni preferiscono evitare completamente la rete Wi-Fi. A volte queste indicazioni vengono fornite tramite una raccomandazione agli utenti di connettersi direttamente a una rete cablata. In alcuni casi, l'ordine di binding della rete potrebbe avere la connessione wireless preferita e continuare a usare questa connessione anche se il PC è connesso alla connessione cablata. Per evitare questo comportamento imprevisto, configurare l'ordine di binding per evitare questo scenario.

### <a name="80211-power-save-protocol"></a>protocollo di risparmio energetico di 802,11

Se l'organizzazione usa punti di accesso wireless o router che non supportano il protocollo di risparmio energia di 802,11, è possibile che si verifichino chiamate cadute o una qualità scadente delle chiamate in Microsoft teams in uso su dispositivi Windows. Se non è possibile aggiornare il punto di accesso o i router wireless, è consigliabile aggiornare le impostazioni di Windows Power Plan nei dispositivi in esecuzione a batteria. Ulteriori indicazioni dettagliate e di configurazione sono disponibili nell' [articolo di supporto](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)seguente.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Quali client di teams verranno distribuiti nell'organizzazione?</li><li>Come è possibile distribuire inizialmente i client di teams agli utenti?</li><li>Chi è responsabile della valutazione di endpoint e dispositivi per la convalida che soddisfano i requisiti dei team per un'esperienza di qualità?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il processo che verrà seguito per distribuire i client teams.</li><li>Valutare gli endpoint e i dispositivi ed eseguire e correggere i requisiti.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivi per Teams

Microsoft teams può essere usato per le riunioni o come sistema telefonico. Quando si usano queste funzionalità, il dispositivo di interfaccia usato per i team svolge un ruolo importante nell'esperienza utente.

L'uso di un altoparlante e un microfono incorporati nel PC può sembrare accettabile per l'utente che ha questa configurazione. Ma in genere, questi dispositivi non sono ottimizzati per l'annullamento del rumore e qualsiasi tipo di rumore ambientale può avere un impatto a valle sugli altri utenti della chiamata. Sfruttando i dispositivi ottimizzati per questi scenari, sarà utile garantire un'esperienza di alta qualità.

Ogni dispositivo deve soddisfare le esigenze degli utenti. È necessario adattare dispositivi come auricolari per i diversi tipi di utenti e casi di utilizzo nell'organizzazione.
Un esercizio di mapping da persona a dispositivo deve essere completato come parte del processo di pianificazione.

Dopo aver selezionato i dispositivi, includerli nel piano di test pilota per la convalida finale. È necessario sfruttare i sondaggi durante il progetto pilota per raccogliere feedback per verificare che la strategia del dispositivo sia ottimale.

> [!NOTE]
> In questo momento, ti consigliamo di usare i dispositivi audio certificati tramite il programma di certificazione Skype for business. Per trovare i dispositivi certificati in questo programma, vedere i [dispositivi USB certificati per il catalogo di soluzioni Skype for business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Scegli la strategia di dispositivo globale dell'organizzazione per le esperienze dell'utente e della sala riunioni.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Completare un esercizio di mapping da persona a dispositivo per l'organizzazione.</li><li>Documentare il processo per ottenere dispositivi per utenti e sale riunioni.</li><li>Documentare il processo per la distribuzione e la configurazione di dispositivi per utenti e sale riunioni.</li><li>Acquistare i dispositivi iniziali per iniziare la distribuzione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->