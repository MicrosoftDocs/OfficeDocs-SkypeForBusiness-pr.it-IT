---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786024"
---
# <a name="contoso-case-study-phone-system"></a>Case study Contoso: Sistema telefonico

A seconda della posizione geografica e di altri fattori, Contoso aveva uffici che usavano le seguenti soluzioni di telefonia:

- Tipo di sito A: Skype for Business VoIP aziendale

- Tipo di sito B: sistemi di telefonia legacy tradizionali

- Tipo di sito C: Combinazione dei sistemi di telefonia legacy VoIP aziendale Skype for Business


Per implementare una soluzione Sistema telefonico Microsoft per l'intera organizzazione, Contoso ha dovuto determinare per ogni tipo di sito quale delle seguenti opzioni verrebbe usata con il Sistema telefonico per connettersi alla rete &mdash; &mdash; PSTN (Public Switched Telephone Network):

- Sistema telefonico con piano per chiamate 

- Sistema telefonico con gestore PSTN tramite routing diretto 

- Combinazione di Sistema telefonico con Piano per chiamate e Sistema telefonico con un proprio gestore PSTN attraverso l'instradamento diretto
 
Per determinare la soluzione giusta per la propria organizzazione, Contoso ha utilizzato le soluzioni di telefonia [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) e le chiamate di sessione di Ignite 2019 [in Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo di sito A: Skype for Business VoIP aziendale 

Contoso Skype for Business VoIP aziendale è stato configurato come hub e parla. C'era una posizione centrale che ha mantenuto il gateway PSTN nell'area geografica che ha fornito la connessione alla rete PSTN per gli utenti VoIP aziendale Skype for Business nel paese. Spesso questi uffici satellitari non hanno un proprio indirizzo Internet in uscita. I numeri per questi utenti risiedevano nel trunk SIP che si connette a un database SBC esistente. 

Per determinare se il controller SBC già distribuito è certificato per l'instradamento diretto e il bypass multimediale, Contoso ha controllato l'elenco dei controller dei confini della sessione [certificati per il routing diretto.](direct-routing-border-controllers.md)  

Le abitudini di composizione dell'utente erano di comporre un utente nel sistema di telefonia legacy utilizzando un'estensione, anche quando l'utente dispone di un client Skype for Business disponibile per l'audio peer-to-peer. 

Contoso ha basato la decisione sulle domande seguenti:

- D. È necessario mantenere le funzionalità fornite dalla distribuzione locale?<br>
  A. No 

- D. È necessario interoperabilità con sistemi PBX di terze parti e altri dispositivi di telefonia?<br>
  A. No 

- D. È necessario conservare l'attuale gestore di terze parti?<br> A. Sì (paesi regolamentati) e No 

- D. È necessario distribuire il ROI nei PC SB?<br> A. Sì e no  

- D. I Piani per chiamate PSTN Microsoft sono disponibili in questa area geografica?<br> A. Sì e no 

In base alle risposte alle loro domande, Contoso ha deciso di:

- Spostare gli utenti che si trovano in un'area in cui i piani per le chiamate PSTN sono disponibili nel Sistema telefonico con Piani per chiamate. 

- Spostare gli utenti che non si trovano in un'area geografica in cui sono disponibili i piani di chiamata PSTN, gli utenti che si trovano in un sito in cui il ROI dei PC non sono ancora stati soddisfatti e gli utenti che risiedono in un paese che ha normative di telefonia al Sistema telefonico con instradamento diretto. 

Il diagramma seguente mostra la distribuzione iniziale di Skype for Business VoIP aziendale distribuzione e come è stata eseguita la migrazione di questa distribuzione ai Piani per chiamate Microsoft e all'instradamento diretto:

![Diagramma che mostra gli stati prima e dopo](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo di sito B: sistemi di telefonia legacy tradizionali

Contoso ha molti uffici che sfruttano i sistemi di telefonia legacy. C'era un sottoinsieme di utenti che avevano un numero di telefono E1.64, mentre altri avevano solo un interno. Questi numeri risiedevano nel trunk TDM al gateway PSTN. La composizione tra siti è stata configurata sfruttando un codice di sito davanti all'interno per determinare dove instradare la chiamata. Le abitudini di composizione degli utenti erano di chiamata per interno.   

Contoso ha basato la decisione sulle domande seguenti:

- D. È necessario mantenere le funzionalità fornite dalla distribuzione locale?<br>
  A. No 

- D. È necessario interoperabilità con sistemi PBX di terze parti e altri dispositivi di telefonia?<br> A. Sì

- D. È necessario conservare l'attuale gestore di terze parti?<br> A. No 

- D. Il piano per le chiamate DI Microsoft PSTN è disponibile nella nostra area geografica?<br> A. Sì e no 

In base alle risposte alle loro domande, Contoso ha deciso di: 

- Spostare gli utenti che si trovano in un'area in cui i piani per le chiamate PSTN sono disponibili nel Sistema telefonico con Piani per chiamate. 

- Spostare gli utenti che non si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili nel Sistema telefonico con instradamento diretto. 

- Mantenere una connessione PSTN a dispositivi analogici di importanza fondamentale per l'azienda.

I diagrammi seguenti mostrano la distribuzione di sistema legacy originale con i siti remoti e la migrazione a una distribuzione di routing diretto con l'ottimizzazione dei supporti locali:

**Distribuzione legacy originale**  
 ![ Diagramma che mostra gli stati prima e dopo](media/voice-case-study-2.png)


**Distribuzione con routing diretto**

![Diagramma che mostra gli stati prima e dopo](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo di sito C: Combinazione dei sistemi di telefonia legacy VoIP aziendale Skype for Business e tradizionali

Contoso Skype for Business VoIP aziendale i numeri degli utenti risiedono nel trunk SIP al sistema SBC dal gestore. I numeri dei sistemi di telefonia tradizionali risiedevano nel trunk TDM al gateway PSTN.   

Contoso ha basato la decisione sulle domande seguenti:

- D. È necessario mantenere le funzionalità fornite dalla distribuzione locale?<br>
  A. No 

- D. È necessario interoperabilità con sistemi PBX di terze parti e altri dispositivi di telefonia?<br> A. No 

- D. È necessario conservare l'attuale gestore di terze parti?<br> A. No 

- D. È necessario distribuire il ROI nei PC SB?<br> A. Sì e no  

- D. Il piano chiamate PSTN di Microsoft è disponibile in questa area geografica?<br> A. No 

In base alle risposte alle loro domande, Contoso ha deciso quanto segue: 

- Per gli utenti della telefonia legacy che saranno abilitati per il routing diretto, Contoso ha portato i numeri dal trunk TDM al trunk SIP per SBC, poiché SBC è certificato per l'instradamento diretto. 

- Per supportare un sottoinsieme di utenti che passano al Sistema telefonico e per consentire il routing continuo attraverso il sistema legacy, il sistema di telefonia legacy è stato configurato come hop successivo al sistema SBC.   

- Inoltre, per incoraggiare il cambiamento del comportamento dell'utente e rimuovere la dipendenza dalla composizione delle estensioni interso e interne al sito, Contoso ha fornito indicazioni per usare Teams per tutte le chiamate interne.  

I seguenti diagrammi mostrano la distribuzione originale di Skype for Business VoIP aziendale sistema di telefonia legacy e la migrazione a una distribuzione mista con routing diretto:

**Distribuzione mista originale** 
 ![ Diagramma che mostra lo stato precedente](media/voice-case-study-4.png)

**Distribuzione mista con routing diretto** 
 ![ Diagramma che mostra lo stato precedente](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Piani di chiamata

Per determinare i requisiti di configurazione per i Piani per chiamate, Contoso ha esaminato le decisioni di distribuzione di base [del Piano per chiamate.](calling-plan-landing-page.md#core-deployment-decisions) Sono state prese le decisioni risultanti: 

- D. Gli utenti devono effettuare chiamate internazionali?<br> A. Sì 

- D. Gli utenti hanno ciascuno un numero di telefono DID diretto verso l'interno?<br> A. Non oggi. Tutti gli utenti abilitati riceveranno un DID. 

- D. Si vuole mascherare o disabilitare l'ID chiamante?<br> A. L'ID chiamante di un utente verrà mascherato al numero locale di Contoso. 


## <a name="direct-routing"></a>Routing diretto

Contoso ha partecipato a Ignite per restare al corrente sulle funzionalità di Office 365, incluse quelle disponibili con Sistema telefonico e Routing diretto. I dirigenti tecnici e architetti hanno usato le indicazioni fornite durante la Ignite 2019 per determinare la direzione.  Sessioni chiave usate: 

- [Pianificare il successo con l'instradamento diretto di Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Aggiornamenti per il routing diretto](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configurazione

### <a name="calling-plans-sites"></a>Siti piani per chiamate

Per ottenere licenze e assegnare numeri di telefono agli utenti, Contoso ha seguito la procedura descritta in [Configurare i piani per chiamate.](set-up-calling-plans.md) 

Dato il numero di utenti a cui assegnare numeri di telefono, Contoso ha deciso di usare PowerShell per assegnare i numeri di telefono. Per informazioni su come assegnare numeri usando PowerShell, oltre ad &mdash; altre &mdash; impostazioni, Contoso ha usato la panoramica [di Teams su PowerShell.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Siti di routing diretto

Per connettere l'infrastruttura di telefonia locale di Contoso a Microsoft Teams, l'amministratore di Contoso ha seguito la procedura [descritta](direct-routing-configure.md) in Configurare l'instradamento diretto ed esaminato il video Routing diretto in [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) per indicazioni.  Contoso ha anche fatto riferimento alla documentazione relativa alla distribuzione del routing diretto da parte del fornitore di SBC certificato. 

Dopo la configurazione dell'instradamento diretto tra SBC e Sistema telefonico Microsoft, è necessario che Contoso testi la configurazione. A questo scopo, gli amministratori di Contoso hanno usato il client Tester SIP discusso nella sessione Aggiornamenti per il routing diretto [di Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) La documentazione e lo script client tester SIP sono stati scaricati dallo script di PowerShell per testare le connessioni al controller dei confini della sessione di routing diretto.   


### <a name="local-media-optimization"></a>Ottimizzazione degli elementi multimediali locali

Contoso ha visto l'opportunità di sfruttare l'ottimizzazione multimediale locale nelle diverse aree geografiche del mondo. Gli scenari supportati per Contoso sono descritti in Ottimizzazione supporto locale [per il routing diretto.](direct-routing-media-optimization.md) La configurazione dell'ottimizzazione degli elementi multimediali locali è stata completata seguendo le indicazioni del fornitore di SBC e di Microsoft. I passaggi di configurazione per l'ottimizzazione del supporto locale includono: 

- Configurare l'utente e i siti SBC 

- Configurare SBC in base alle specifiche del fornitore di SBC, 

- Aggiungere indirizzi IP attendibili esterni a ogni sito usato per l'ottimizzazione del supporto locale    

- Definire la topologia della rete 

- Definire la topologia della rete virtuale 

- Determinare la modalità: Ignora sempre o Solo per gli utenti locali 

## <a name="networking-considerations"></a>Considerazioni sulla rete

Contoso aveva diversi utenti che dovevano lavorare in remoto per un lungo periodo di tempo dopo l'a attivazione del Sistema telefonico. Gli utenti usava la rete VPN per accedere a determinate applicazioni Line of Business. Mentre si è connessi alla rete VPN, gli utenti del Sistema telefonico hanno riscontrato una riduzione della qualità delle chiamate. 

Per risolvere il problema della qualità, Contoso ha implementato lo split tunneling VPN, che consentiva al traffico di Office 365 di attraversare Internet mentre la connessione alle app interne rimaneva nella VPN. Per implementare lo split tunneling VPN, Contoso ha seguito le istruzioni per implementare [lo split tunneling VPN per Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)  

 





