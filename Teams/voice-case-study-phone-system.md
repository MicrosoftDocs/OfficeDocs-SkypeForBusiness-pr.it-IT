---
title: 'Case study contoso: Sistema telefonico per una società multinazionale'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams case study sulla voce per società multinazionali: sistema telefonico'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823667"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Case study contoso: Sistema telefonico per una società multinazionale

A seconda della posizione geografica e di altri fattori, Contoso aveva uffici con le seguenti soluzioni di telefonia:

- Tipo di sito A: Skype for Business VoIP aziendale

- Sito tipo B: sistemi di telefonia legacy tradizionali

- Tipo di sito C: combinazione di Skype for Business VoIP aziendale e sistemi di telefonia legacy tradizionali


Per implementare una soluzione Telefono Microsoft System per l'intera organizzazione, Contoso doveva determinare&mdash;per ogni tipo&mdash;di sito quale delle seguenti opzioni sarebbe stata usata con Sistema telefonico per connettersi alla rete PSTN (Public Switched Telephone Network):

- Sistema telefonico con piano per chiamate 

- Sistema telefonico con il proprio gestore PSTN tramite Direct Routing 

- Combinazione di Sistema telefonico con Piano per chiamate e Sistema telefonico con il proprio operatore PSTN tramite Direct Routing
 
Per determinare la soluzione giusta per l'organizzazione, Contoso ha usato [Plan your Teams voice solution](/microsoftteams/cloud-voice-landing-page) e la sessione Calling di Ignite 2019 [in Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo di sito A: Skype for Business VoIP aziendale 

Contoso Skype for Business VoIP aziendale è stato configurato come hub e ha parlato. C'era una posizione centrale che conservava il gateway PSTN nell'area geografica che forniva la connessione alla rete PSTN per gli utenti Skype for Business VoIP aziendale nel paese. Spesso questi uffici satellitari non hanno un proprio uscita Internet. The numbers for these users resided on the SIP trunk connecting to an existing SBC. 

Per determinare se la scheda SBC già distribuita è certificata per direct routing e media bypass, Contoso ha controllato [l'elenco dei controller dei confini della sessione certificati per il routing diretto](direct-routing-border-controllers.md).  

Le abitudini di composizione dell'utente erano di comporre un utente sul sistema di telefonia legacy utilizzando un'estensione, anche quando l'utente ha un client di Skype for Business disponibile per l'audio peer-to-peer. 

Contoso ha basato la propria decisione sulle domande seguenti:

- D. È necessario conservare le funzionalità fornite dalla distribuzione locale?<br>
  Un. No 

- D. È necessario interagire con sistemi PBX di terze parti e altri dispositivi di telefonia?<br>
  Un. No 

- D. È necessario mantenere l'attuale gestore di terze parti?<br> Un. Sì (paesi regolamentati) e No 

- D. Dobbiamo distribuire il ROI nelle schede SBC?<br> Un. Sì e no  

- D. I piani per chiamate PSTN Microsoft sono disponibili in questa area geografica?<br> Un. Sì e no 

In base alle risposte alle loro domande, Contoso ha deciso di:

- Spostare gli utenti che si trovano in un'area geografica in cui i piani per chiamate PSTN sono disponibili per Sistema telefonico con Piani per chiamate. 

- Spostare gli utenti che non si trovano in un'area geografica in cui sono disponibili piani di chiamate PSTN, gli utenti che si trovano in un sito in cui il ROI nelle SBC non è ancora stato soddisfatto e gli utenti che risiedevano in un paese con normative di telefonia da Sistema telefonico con Direct Routing. 

Il diagramma seguente illustra la distribuzione iniziale Skype for Business VoIP aziendale e come è stata eseguita la migrazione di questa distribuzione sia in Piani per chiamate Microsoft che in Routing diretto:

![Il diagramma mostra gli stati prima e dopo.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Sito tipo B: sistemi di telefonia legacy tradizionali

Contoso aveva molti uffici che sfruttavano i sistemi di telefonia legacy. C'erano un sottoinsieme di utenti che avevano un numero di telefono E1.64, mentre altri avevano solo un'estensione. Questi numeri si trovano nel trunk TDM del gateway PSTN. La composizione intrasito è stata configurata sfruttando un codice sito davanti all'estensione per determinare dove instradare la chiamata. Le abitudini di composizione degli utenti erano di comporre per estensione.   

Contoso ha basato la propria decisione sulle domande seguenti:

- D. È necessario conservare le funzionalità fornite dalla distribuzione locale?<br>
  Un. No 

- D. È necessario interagire con sistemi PBX di terze parti e altri dispositivi di telefonia?<br> Un. Sì

- D. È necessario mantenere l'attuale gestore di terze parti?<br> Un. No 

- D. Il piano per chiamate PSTN Microsoft è disponibile nella nostra area geografica?<br> Un. Sì e no 

In base alle risposte alle loro domande, Contoso ha deciso di: 

- Spostare gli utenti che si trovano in un'area geografica in cui i piani per chiamate PSTN sono disponibili per Sistema telefonico con Piani per chiamate. 

- Spostare gli utenti che non si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili per Sistema telefonico con routing diretto. 

- Mantieni una connessione PSTN ai dispositivi analogici aziendali critici.

I diagrammi seguenti mostrano la distribuzione di sistema legacy originale con i siti remoti e la migrazione a una distribuzione direct routing con Ottimizzazione multimediale locale:

**Distribuzione legacy** 
![ originale Un diagramma mostra gli stati prima e dopo.](media/voice-case-study-2.png)


**Distribuzione con routing diretto**

![Diagramma che mostra gli stati prima e dopo.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo di sito C: combinazione di Skype for Business VoIP aziendale e sistemi di telefonia legacy tradizionali

Contoso Skype for Business VoIP aziendale numeri degli utenti si trovano nel trunk SIP per SBC dal gestore telefonico. I numeri per i sistemi di telefonia tradizionali risiedevano sul trunk TDM al gateway PSTN.   

Contoso ha basato la propria decisione sulle domande seguenti:

- D. È necessario conservare le funzionalità fornite dalla distribuzione locale?<br>
  Un. No 

- D. È necessario interagire con sistemi PBX di terze parti e altri dispositivi di telefonia?<br> Un. No 

- D. È necessario mantenere l'attuale gestore di terze parti?<br> Un. No 

- D. Dobbiamo distribuire il ROI nelle schede SBC?<br> Un. Sì e no  

- D. Il piano per le chiamate PSTN Microsoft è disponibile in questa area geografica?<br> Un. No 

In base alle risposte alle loro domande, Contoso ha deciso quanto segue: 

- Per gli utenti di telefonia legacy che saranno abilitati per il routing diretto, Contoso ha effettuato il trasferimento dei numeri dal trunk TDM al trunk SIP per SBC, poiché la SBC è certificata per direct routing. 

- Per supportare un sottoinsieme di utenti che passano a Sistema telefonico e consentire il routing continuo attraverso il sistema legacy, il sistema di telefonia legacy è stato configurato come passaggio successivo alla scheda SBC.   

- Inoltre, per incoraggiare la modifica del comportamento dell'utente e rimuovere la dipendenza dalla composizione delle estensioni intersito e intrasito, Contoso ha fornito indicazioni su come usare Teams per tutte le chiamate interne.  

I diagrammi seguenti mostrano la distribuzione originale del sistema di telefonia Skype for Business VoIP aziendale e legacy e la migrazione a una distribuzione mista tramite routing diretto:

**Distribuzione mista**
![ originale Diagramma 1 che mostra lo stato Prima.](media/voice-case-study-4.png)

**Distribuzione mista con routing**
![ diretto Diagramma 2 che mostra lo stato Prima.](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Piani di chiamata

Per determinare i requisiti di configurazione per i piani per chiamate, Contoso ha esaminato le [decisioni di distribuzione di base del Piano per chiamate](calling-plan-landing-page.md#core-deployment-decisions). Le decisioni risultanti sono state prese: 

- D. Gli utenti hanno bisogno di chiamate internazionali?<br> Un. Sì 

- D. Ogni utente ha un numero di telefono DID diretto verso l'interno?<br> R. Non oggi. Tutti gli utenti abilitati riceveranno un did. 

- D. Si vuole mascherare o disabilitare l'ID chiamante?<br> Un. L'ID chiamante di un utente verrà mascherato al numero locale di Contoso. 


## <a name="direct-routing"></a>Routing diretto

Contoso ha partecipato a Ignite per mantenersi aggiornati sulle caratteristiche di Office 365, incluse quelle disponibili con Telefono sistema e routing diretto. I dirigenti tecnici e gli architetti hanno usato le indicazioni fornite durante l'Ignite 2019 per determinarne la direzione.  Sessioni principali utilizzate: 

- [Pianificare il successo con Microsoft Teams Direct Routing](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [Aggiornamenti per il routing diretto](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>Configurazione

### <a name="calling-plans-sites"></a>Siti piani per chiamate

Per ottenere licenze e assegnare numeri di telefono agli utenti, Contoso ha seguito la procedura descritta in [Configurare i piani per chiamate](set-up-calling-plans.md). 

A causa del numero di utenti a cui era necessario assegnare numeri di telefono, Contoso ha deciso di usare PowerShell per assegnare i numeri di telefono. Per informazioni su come assegnare numeri con PowerShell&mdash;oltre ad altre impostazioni&mdash;, Contoso ha usato la [panoramica di Teams PowerShell](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Siti di routing diretto

Per connettere l'infrastruttura di telefonia locale di Contoso a Microsoft Teams, l'amministratore di Contoso ha seguito la procedura descritta in [Configurare routing diretto](direct-routing-configure.md) ed esaminato il video [Routing diretto in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) per indicazioni.  Contoso ha anche fatto riferimento alla documentazione relativa alla distribuzione diretta del routing da parte del fornitore SBC certificato. 

Dopo aver configurato il routing diretto tra SBC e Telefono Microsoft Sistema, era necessario che Contoso testasse la configurazione. A tale scopo, gli amministratori di Contoso hanno usato il client Sip Tester, discusso nella [sessione "Aggiornamenti per il routing diretto" a Ignite 2019](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138). Lo script client SIP Tester e la documentazione sono stati scaricati dallo script di PowerShell per testare le connessioni del controller dei confini della sessione di routing diretto.   


### <a name="local-media-optimization"></a>Ottimizzazione multimediale locale

Contoso ha visto l'opportunità di sfruttare Ottimizzazione multimediale locale nelle diverse aree geografiche del mondo. Gli scenari supportati per Contoso sono descritti in [Ottimizzazione multimediale locale per il routing diretto](direct-routing-media-optimization.md). La configurazione dell'ottimizzazione multimediale locale è stata completata seguendo le indicazioni del fornitore di SBC e di Microsoft. I passaggi di configurazione per Ottimizzazione multimediale locale includono: 

- Configurare i siti utente e SBC 

- Configurare SBC in base alle specifiche dei fornitori di SBC, 

- Aggiungere indirizzi IP attendibili esterni a ogni sito usato per Ottimizzazione multimediale locale    

- Definire la topologia della rete 

- Definire la topologia della rete virtuale 

- Determinare la modalità: Ignora sempre o Solo per gli utenti locali 

## <a name="networking-considerations"></a>Considerazioni sulla rete

Contoso aveva diversi utenti che dovevano lavorare in remoto per un periodo prolungato di tempo dopo l'abilitazione per Sistema telefonico. Gli utenti hanno usato la VPN per accedere ad alcune applicazioni Line of Business. Mentre si usa la VPN, gli utenti Sistema telefonico hanno riscontrato una riduzione della qualità delle chiamate. 

Per risolvere il problema di qualità, Contoso ha implementato il tunneling di divisione VPN, che ha consentito al traffico Office 365 di attraversare Internet mentre la connessione alle app interne rimaneva nella VPN. Per implementare il tunneling diviso per vpn, Contoso ha seguito le indicazioni in [Implementazione del tunneling diviso VPN per Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

