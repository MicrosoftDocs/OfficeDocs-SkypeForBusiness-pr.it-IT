---
title: 'Caso di studio Contoso: Sistema telefonico per una multinazionale'
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
description: 'Teams case study vocale per multinazionali: sistema telefonico'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ee15ef9bb42a28023c86963dd9100797c51edc3
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587145"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Caso di studio Contoso: Sistema telefonico per una multinazionale

A seconda della posizione geografica e di altri fattori, Contoso aveva uffici che usavano le soluzioni di telefonia seguenti:

- Tipo di sito A: Skype for Business VoIP aziendale

- Tipo di sito B: Sistemi di telefonia legacy tradizionali

- Tipo di sito C: Combinazione di Skype for Business VoIP aziendale tradizionali e sistemi di telefonia legacy


Per implementare una soluzione Telefono Microsoft System per l'intera organizzazione, Contoso ha dovuto determinare per ogni tipo di sito quali delle opzioni seguenti verrebbero usate con Sistema telefonico per connettersi alla rete &mdash; &mdash; PSTN (Public Switched Telephone Network):

- Sistema telefonico piano chiamate 

- Sistema telefonico gestore PSTN tramite routing diretto 

- Combinazione di Sistema telefonico piano per chiamate e Sistema telefonico con il proprio gestore PSTN tramite routing diretto
 
Per determinare la soluzione giusta per l'organizzazione, Contoso ha usato le soluzioni di telefonia [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) e la sessione Ignite 2019 [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo di sito A: Skype for Business VoIP aziendale 

Contoso Skype for Business VoIP aziendale è stato configurato come hub e ha parlato. C'era una posizione centrale che ha mantenuto il gateway PSTN nell'area geografica che ha fornito la connessione alla rete PSTN per gli utenti Skype for Business VoIP aziendale nel paese. Spesso questi uffici satellitari non hanno una propria uscita Internet. I numeri di questi utenti risiedevano nel trunk SIP che si connetteva a un SBC esistente. 

Per determinare se la SBC già distribuita è certificata per il routing diretto e il bypass multimediale, Contoso ha controllato l'elenco dei controller di confine di sessione [certificati per il routing diretto.](direct-routing-border-controllers.md)  

Le abitudini di composizione dell'utente erano di comporre un utente nel sistema di telefonia legacy usando un'estensione, anche quando l'utente ha un client Skype for Business disponibile per l'audio peer-to-peer. 

Contoso ha basato la propria decisione sulle domande seguenti:

- Q. È necessario mantenere le funzionalità fornite dalla distribuzione locale?<br>
  A. No 

- Q. È necessario interagire con sistemi PBX di terze parti e altre apparecchiature di telefonia?<br>
  A. No 

- Q. È necessario conservare l'attuale gestore di terze parti?<br> A. Sì (paesi regolamentati) e No 

- Q. È necessario distribuire il ROI sugli SBC?<br> A. Sì e no  

- Q. I piani per chiamate PSTN Microsoft sono disponibili in questa area geografica?<br> A. Sì e no 

In base alle risposte alle loro domande, Contoso ha deciso di:

- Spostare gli utenti che si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili Sistema telefonico piani per chiamate. 

- Spostare gli utenti che non si trovano in un'area geografica in cui sono disponibili piani per le chiamate PSTN, gli utenti che si trovano in un sito in cui il ROI degli SBC deve ancora essere soddisfatto e gli utenti che risiedono in un paese che ha normative di telefonia da Sistema telefonico con routing diretto. 

Il diagramma seguente mostra la distribuzione Skype for Business VoIP aziendale distribuzione iniziale e come è stata eseguita la migrazione di questa distribuzione ai piani per chiamate Microsoft e al routing diretto:

![Il diagramma mostra gli stati prima e dopo.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo di sito B: Sistemi di telefonia legacy tradizionali

Contoso aveva molti uffici che sfruttavano sistemi di telefonia legacy. C'era un sottoinsieme di utenti con un numero di telefono E1.64, mentre altri avevano solo un interno. Questi numeri si trovavano nel trunk TDM al gateway PSTN. La composizione all'interno del sito è stata configurata usando un codice del sito davanti all'interno per determinare dove instradare la chiamata. Le abitudini di composizione degli utenti erano di comporre per interno.   

Contoso ha basato la propria decisione sulle domande seguenti:

- Q. È necessario mantenere le funzionalità fornite dalla distribuzione locale?<br>
  A. No 

- Q. È necessario interagire con sistemi PBX di terze parti e altre apparecchiature di telefonia?<br> A. Sì

- Q. È necessario conservare l'attuale gestore di terze parti?<br> A. No 

- Q. Il piano per le chiamate PSTN di Microsoft è disponibile nella nostra area geografica?<br> A. Sì e no 

In base alle risposte alle loro domande, Contoso ha deciso di: 

- Spostare gli utenti che si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili Sistema telefonico piani per chiamate. 

- Spostare gli utenti che non si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili Sistema telefonico routing diretto. 

- Mantenere una connessione PSTN a dispositivi analogici aziendali critici.

I diagrammi seguenti mostrano la distribuzione del sistema legacy originale con siti remoti e la migrazione a una distribuzione di Routing diretto con l'ottimizzazione del supporto locale:

**Distribuzione legacy originale**  
 ![ Un diagramma mostra gli stati prima e dopo.](media/voice-case-study-2.png)


**Distribuzione con routing diretto**

![Diagramma che mostra gli stati prima e dopo.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo di sito C: Combinazione di Skype for Business VoIP aziendale tradizionali sistemi di telefonia legacy

Contoso Skype for Business VoIP aziendale i numeri degli utenti risiedono nel trunk SIP alla SBC dal gestore. I numeri dei sistemi di telefonia tradizionali si trovavano nel trunk TDM al gateway PSTN.   

Contoso ha basato la propria decisione sulle domande seguenti:

- Q. È necessario mantenere le funzionalità fornite dalla distribuzione locale?<br>
  A. No 

- Q. È necessario interagire con sistemi PBX di terze parti e altre apparecchiature di telefonia?<br> A. No 

- Q. È necessario conservare l'attuale gestore di terze parti?<br> A. No 

- Q. È necessario distribuire il ROI sugli SBC?<br> A. Sì e no  

- Q. Il piano chiamate PSTN di Microsoft è disponibile in questa area geografica?<br> A. No 

In base alle risposte alle loro domande, Contoso ha deciso quanto segue: 

- Per gli utenti di telefonia legacy che verranno abilitati per il routing diretto, Contoso ha portato i numeri dal trunk TDM al trunk SIP per SBC, perché SBC è certificato per il routing diretto. 

- Per supportare un sottoinsieme di utenti che si spostano in Sistema telefonico e per consentire il routing continuo attraverso il sistema legacy, il sistema di telefonia legacy è stato configurato come hop successivo al sistema SBC.   

- Inoltre, per incoraggiare il cambiamento del comportamento degli utenti e rimuovere la dipendenza dalla composizione interna e interna al sito, Contoso ha fornito indicazioni per usare Teams per tutte le chiamate interne.  

I diagrammi seguenti mostrano la distribuzione originale Skype for Business VoIP aziendale sistema di telefonia legacy e la migrazione a una distribuzione mista con Routing diretto:

**Distribuzione mista originale** 
 ![ Diagramma 1 che mostra lo stato precedente.](media/voice-case-study-4.png)

**Distribuzione mista con routing diretto** 
 ![ Diagramma 2 che mostra lo stato precedente.](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Piani di chiamata

Per determinare i requisiti di configurazione per i piani per chiamate, Contoso ha esaminato le decisioni di distribuzione principali del piano [di chiamata.](calling-plan-landing-page.md#core-deployment-decisions) Le decisioni risultanti sono state prese: 

- Q. Gli utenti hanno bisogno di chiamate internazionali?<br> A. Sì 

- Q. Gli utenti hanno un numero di telefono DID diretto verso l'interno?<br> A. Non oggi. Tutti gli utenti abilitati riceveranno un DID. 

- Q. Si vuole mascherare o disabilitare l'ID chiamante?<br> A. L'ID chiamante di un utente verrà mascherato al numero locale di Contoso. 


## <a name="direct-routing"></a>Routing diretto

Contoso ha partecipato a Ignite per rimanere al corrente delle Office 365, incluse quelle disponibili con Telefono sistema e Routing diretto. I dirigenti tecnici e gli architetti hanno usato le indicazioni fornite durante Ignite 2019 per determinarne la direzione.  Sessioni chiave usate: 

- [Pianificare il successo con Microsoft Teams Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Aggiornamenti per il routing diretto](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configurazione

### <a name="calling-plans-sites"></a>Siti dei piani di chiamata

Per ottenere licenze e assegnare numeri di telefono agli utenti, Contoso ha seguito la procedura descritta in [Configurare i piani per chiamate.](set-up-calling-plans.md) 

A causa del numero di utenti a cui era necessario assegnare i numeri di telefono, Contoso ha deciso di usare PowerShell per assegnare i numeri di telefono. Per informazioni su come assegnare numeri usando PowerShell oltre ad altre impostazioni, Contoso ha usato la &mdash; &mdash; Teams panoramica di [PowerShell.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Siti di routing diretto

Per connettere l'infrastruttura di telefonia locale di Contoso a Microsoft Teams, l'amministratore di Contoso ha seguito i passaggi descritti in [Configurare](direct-routing-configure.md) il routing diretto e ha esaminato il video Routing diretto [in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) per istruzioni.  Contoso ha anche fatto riferimento alla documentazione relativa alla distribuzione del routing diretto da parte del fornitore SBC certificato. 

Dopo aver configurato il routing diretto tra il sistema SBC e Telefono Microsoft, è stato necessario che Contoso testare la configurazione. A questo scopo, gli amministratori di Contoso hanno usato il client TESTER SIP discusso nella sessione Aggiornamenti per il routing diretto in [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) Lo script client e la documentazione del tester SIP sono stati scaricati dallo script di PowerShell per testare le connessioni di Direct Routing Session Border Controller.   


### <a name="local-media-optimization"></a>Ottimizzazione del supporto locale

Contoso ha avuto l'opportunità di sfruttare l'Ottimizzazione multimediale locale nelle diverse aree geografiche del globo. Gli scenari supportati per Contoso sono descritti in [Ottimizzazione multimediale locale per il routing diretto.](direct-routing-media-optimization.md) La configurazione dell'ottimizzazione dei supporti multimediali locali è stata completata seguendo le indicazioni del fornitore SBC e di Microsoft. I passaggi di configurazione per Ottimizzazione file multimediali locali includono: 

- Configurare l'utente e i siti SBC 

- Configurare SBC in base alla specifica del fornitore SBC, 

- Aggiungere indirizzi IP attendibili esterni a ogni sito usato per l'ottimizzazione dei supporti locali    

- Definire la topologia di rete 

- Definire la topologia della rete virtuale 

- Determinare la modalità: Ignora sempre o Solo per gli utenti locali 

## <a name="networking-considerations"></a>Considerazioni sulla rete

Contoso aveva un certo numero di utenti che dovevano lavorare in remoto per un lungo periodo di tempo dopo essere stati abilitati per Sistema telefonico. Gli utenti hanno usato vpn per accedere a determinate applicazioni Line of Business. Mentre si è connessi a una rete VPN, Sistema telefonico utenti hanno riscontrato una riduzione della qualità delle chiamate. 

Per risolvere il problema della qualità, Contoso ha implementato il split tunneling VPN, che ha consentito al traffico Office 365 di attraversare Internet mentre la connessione alle app interne rimaneva nella VPN. Per implementare il split tunneling VPN, Contoso ha seguito le indicazioni in Implementazione del [split tunneling VPN per Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

