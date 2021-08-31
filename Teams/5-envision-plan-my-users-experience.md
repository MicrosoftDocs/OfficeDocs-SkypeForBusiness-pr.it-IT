---
title: Pianificare l'esperienza degli utenti Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scegliere Teams client, pianificare la qualità dell'endpoint, ottenere consigli per la distribuzione Wi-Fi endpoint e la scelta di dispositivi audio.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5176f40886bdc086df43a130cb9d8414bd8f40a3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732965"
---
# <a name="plan-my-users-experience"></a>Pianificare l'esperienza degli utenti

Questo articolo fornisce una panoramica dei requisiti per identificare correttamente gli elementi della distribuzione di servizi vocali cloud che influiscono direttamente sull'esperienza degli utenti. La preparazione di questi elementi prima della distribuzione aumenta le possibilità di offrire agli utenti un'esperienza affidabile e di alta qualità. 

## <a name="client-deployment"></a>Distribuzione client

Microsoft Teams sono disponibili client per web, desktop (Windows e Mac) e per dispositivi mobili (Android e iOS). Per altre informazioni sulla modalità di installazione del desktop (Windows Mac) e dei client mobili, vedere Ottenere [i client per Microsoft Teams](./get-clients.md).

## <a name="client-updates"></a>Aggiornamenti del client

Uno dei vantaggi principali di Teams è che il cliente viene aggiornato automaticamente. I client nel PC e nel Mac vengono aggiornati usando un processo in background che controlla la presenza di nuove build e scarica il nuovo client quando l'app è inattiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Pianificare la qualità dell'endpoint

Come si può vedere dal diagramma seguente, gli endpoint sono un importante elemento fondamentale per offrire agli utenti un'esperienza di qualità.

![Diagramma che descrive i tre componenti della qualità.](media/plan-my-users-experience-image1.png "Diagramma che descrive i tre componenti della qualità e il modo in cui la gestione dei servizi si sovrappone a tutti e tre i componenti. Con lo stato attivo sugli endpoint.")

Teams endpoint possono essere eseguiti su molti dispositivi, tra cui PC, Mac, tablet e dispositivi mobili. Parte dell'esperienza non riguarda solo il dispositivo, ma anche il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono/altoparlante incorporato del dispositivo, gli auricolari o un auricolare ottimizzato. L'uso di un auricolare ottimizzato può arricchire l'esperienza utente generale.

Le indicazioni seguenti sulla pianificazione degli endpoint consentono di garantire all'organizzazione un'esperienza di onboarding efficace con Teams.

## <a name="endpoint-capability"></a>Funzionalità dell'endpoint

La prima parte della pianificazione è garantire che tutti i PC e gli altri dispositivi dell'organizzazione possano essere eseguiti Teams. Questo implica non solo la ricerca dei requisiti hardware, ma anche la comprensione delle altre attività del PC in background. Molte organizzazioni eseguono altri software, tra cui sistemi di rilevamento delle intrusioni e software antimalware, che possono influire sulle prestazioni di base di un dispositivo.

Per informazioni sui requisiti software per Teams client su ogni piattaforma (Web, desktop e dispositivi mobili), vedere Ottenere client per Microsoft Teams [.](./get-clients.md)

## <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente.
I firewall sul lato client possono influire sulla qualità delle chiamate, oltre a impedire che venga stabilita una chiamata. Configurare le esclusioni appropriate nel firewall client in base alle informazioni in Microsoft 365 o Office 365 URL e [intervalli di indirizzi IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Il fornitore di terze parti avrà indicazioni specifiche su come creare le esclusioni.

>[!NOTE]
> Microsoft Teams aggiornerà automaticamente il firewall Windows firewall con una configurazione del firewall appropriata.

## <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi per gli endpoint

È necessario pianificare in modo significativo la distribuzione di una rete Wi-Fi per supportare i carichi di lavoro in tempo reale in Microsoft Teams. Le sezioni seguenti forniscono alcune indicazioni generali che consentono di evitare insidie comuni durante la pianificazione degli endpoint.

### <a name="wi-fi-drivers"></a>Wi-Fi driver

Alcuni Wi-Fi driver possono essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressivi tra i punti di accesso, causando una scarsa qualità delle chiamate.
Non si tratta di un'occorrenza comune, ma è importante assicurarsi che i driver Wi-Fi nel PC siano stati aggiornati e testati prima della distribuzione.

### <a name="wi-fi-bands"></a>Wi-Fi bande

Esistono principalmente due tipi di bande usate nelle apparecchiature Wi-Fi oggi, 2,4 GHz e 5,0 GHz. Se l'organizzazione fornisce entrambe le bande, è consigliabile configurare le impostazioni del driver in modo da preferire la banda da 5,0 GHz. Questa banda è molto più densa in termini di velocità effettiva ed è meno influenzata dalle interferenze osservate nella banda da 2,4 GHz.
Questa raccomandazione presuppone che la banda di rete da 5,0 GHz sia stata ottimizzata correttamente.

### <a name="wi-fi-radio-type"></a>Wi-Fi radio

Pianificare i dispositivi che supportano i tipi di radio Wi-Fi più recente. Se si usa 802.11ac o versione più recente nei dispositivi di cui si effettua il provisioning, è possibile ottenere prestazioni ottimali Wi-Fi prestazioni ottimali.

### <a name="wireless-avoidance"></a>Evitamento wireless

Alcune organizzazioni preferiscono evitare di Wi-Fi del tutto. A volte queste indicazioni vengono fornite tramite un suggerimento agli utenti per connettersi direttamente a una rete cablata. In alcuni casi, l'ordine di associazione della rete potrebbe avere la connessione wireless preferita e continuare a usarla anche se il PC è connesso alla connessione cablata. Per evitare questo comportamento indesiderato, configurare l'ordine di associazione per evitare questo scenario.

### <a name="80211-power-save-protocol"></a>Protocollo Power Save 802.11

Se l'organizzazione usa punti di accesso wireless o router che non supportano il protocollo Power Save 802.11, è possibile che si verifichino chiamate perse o scarsa qualità delle chiamate in Microsoft Teams in esecuzione su Windows dispositivi. Se non è possibile aggiornare il punto di accesso wireless o i router, è consigliabile aggiornare Windows impostazioni di Power Plan nei dispositivi che eseguono l'alimentazione a batteria. Ulteriori informazioni dettagliate e indicazioni sulla configurazione sono disponibili nell'articolo del [supporto tecnico seguente.](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Quali Teams client verranno distribuiti nell'organizzazione?</li><li>Come si distribuiscono inizialmente Teams client agli utenti?</li><li>Who è responsabile della valutazione di endpoint e dispositivi per verificare che soddisfino Teams requisiti di qualità?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il processo che verrà seguito per distribuire Teams client.</li><li>Valutare endpoint e dispositivi ed eseguire e correggere i problemi necessari.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivi per Teams

Microsoft Teams può essere usato per le riunioni o come sistema telefonico. Quando si usano queste funzionalità, il dispositivo di interfaccia usato per Teams svolge un ruolo importante nell'esperienza utente.

L'uso di un altoparlante e di un microfono predefiniti per PC potrebbe sembrare accettabile per l'utente che ha questa configurazione. In genere, tuttavia, questi dispositivi non sono ottimizzati per l'annullamento del rumore e qualsiasi tipo di rumore ambientale può avere un impatto a valle sugli altri utenti della chiamata. L'uso di dispositivi ottimizzati per questi scenari consente di garantire un'esperienza di alta qualità.

Ogni dispositivo deve soddisfare le esigenze degli utenti. È necessario personalizzare i dispositivi, ad esempio le cuffie, per i diversi utenti e i casi di utilizzo dell'organizzazione.
Nell'ambito del processo di pianificazione, è necessario completare un esercizio di mappatura persona-dispositivo.

Dopo aver selezionato i dispositivi, includerli nel piano di test pilota per la convalida finale. Sfruttare i sondaggi durante il progetto pilota per raccogliere feedback per assicurarsi che la strategia del dispositivo sia ottimale.

> [!NOTE]
> Al momento, è consigliabile usare dispositivi audio certificati tramite il programma Skype for Business certificazione. Per trovare i dispositivi certificati in questo programma, vedere i [Microsoft Teams usb](https://products.office.com/microsoft-teams/across-devices/devices) e i dispositivi audio e [video USB.](/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere la strategia generale dei dispositivi dell'organizzazione per le esperienze utente e delle sale riunioni.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Completare un esercizio di mapping persona-dispositivo per l'organizzazione.</li><li>Documentare il processo per ottenere dispositivi per utenti e sale riunioni.</li><li>Documentare il processo di distribuzione e configurazione dei dispositivi per utenti e sale riunioni.</li><li>Procurarsi i dispositivi iniziali per avviare la distribuzione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->