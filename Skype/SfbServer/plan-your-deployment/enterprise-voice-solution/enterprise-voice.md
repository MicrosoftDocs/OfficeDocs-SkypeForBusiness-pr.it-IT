---
title: Pianificare la VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: VoIP aziendale di base sulla pianificazione Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico di utilizzo vocale.
ms.openlocfilehash: 51c197979c5faaf587f63320b4a2dc6c5dc6a06f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829840"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Pianificare la VoIP aziendale in Skype for Business Server
 
VoIP aziendale di base sulla pianificazione Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico di utilizzo vocale.
  
Il processo di distribuzione VoIP aziendale dipende dalla topologia, dall'infrastruttura e dalla VoIP aziendale esistente che si desidera supportare. Le procedure necessarie dipenderanno dalle funzionalità scelte, ma è necessario tenere conto di altre considerazioni sulla pianificazione a livello superiore.
  
In generale, considerare il tipo e il numero di siti che si desidera distribuire e le relative posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che connettono i siti, se si desidera fornire ridondanza e failover per le funzionalità vocali per ogni sito e se si desidera utilizzare apparecchiature PBX esistenti. Esistono alcune considerazioni, ad esempio la disponibilità elevata, da prendere in considerazione quando si pianifica l'Skype for Business Server nel suo complesso. Queste considerazioni sono descritte negli argomenti di questa sezione, in base alle esigenze.
  
## <a name="sites-and-regions"></a>Siti e aree geografiche

Identificare innanzitutto i siti della topologia in cui verranno distribuiti VoIP aziendale e le aree di rete a cui appartengono tali siti. Valutare in particolare il modo in cui verrà fornita la connettività PSTN (Public Switched Telephone Network) a ogni sito. Per motivi logistici e di gestione, le aree a cui appartengono questi siti possono rappresentare un fattore decisivo. Decidere dove verranno distribuiti i gateway in locale, dove verranno distribuiti i Survivable Branch Appliance (SBA) e dove configurare i trunk SIP (in locale o nel sito centrale) in un provider di servizi di telefonia Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Collegamenti di rete tra siti

È inoltre necessario considerare l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i relativi siti di succursale. Se si dispone o si prevede di distribuire collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per fornire la terminazione DID (Direct Inward Dial) locale per gli utenti di tali siti. Se si dispone di collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il servizio Controllo di ammissione di chiamata per il collegamento. Se non si dispone di collegamenti WAN resilienti, ospitare meno di 1000 utenti nel sito di succursale e non sono disponibili amministratori di Skype for Business Server con formazione locale, è consigliabile distribuire un Survivable Branch Appliance nel sito di succursale. Se si ospitano da 1000 a 5000 utenti nel sito di succursale, non si dispone di una connessione WAN resiliente e sono disponibili amministratori di Skype for Business Server formati, è consigliabile distribuire un Survivable Branch Server con un piccolo gateway nel sito di succursale. Prendere inoltre in considerazione l'eventualità di abilitare il bypass multimediale nei collegamenti vincolati se si dispone di un peer gateway che supporta il bypass multimediale.
  
## <a name="estimating-voice-usage-and-traffic"></a>Stima dell'utilizzo e del traffico vocali

Lo Strumento di pianificazione di Microsoft Lync Server 2013 utilizza la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare tale traffico.
  
> Per un livello di **traffico leggero** (una chiamata PSTN per utente all'ora) considerare 15 utenti per porta.
> 
> Per un livello di **traffico medio** (2 chiamate PSTN per utente all'ora) considerare 10 utenti per porta.
> 
> Per un livello di **traffico pesante** (3 chiamate PSTN o più per utente all'ora) considerare 5 utenti per porta.
    
Il numero di porte determina a sua volta il numero di Mediation Server e gateway necessari. I gateway PSTN (Public Switched Telephone Network) distribuiti nella maggior parte delle organizzazioni variano in dimensione da 2 a 960 porte. Sono disponibili anche gateway più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia.
  
Un'organizzazione con 10.000 utenti e traffico medio, ad esempio, necessiterebbe di 1000 porte. Il numero di gateway richiesti sarebbe uguale al numero totale di porte necessarie determinato in base alla capacità totale dei gateway.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componenti, funzionalità e opzioni di VoIP aziendale

Vedere le sezioni seguenti per ulteriori informazioni sulla pianificazione della distribuzione VoIP aziendale distribuzione.
  
- [Componenti necessari per VoIP aziendale in Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Pianificare la connettività PSTN in Skype for Business Server](pstn-connectivity-0.md)
    
- [Impostazioni di rete per le funzionalità VoIP aziendale avanzate in Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Pianificare il controllo di ammissione di chiamata in Skype for Business Server](call-admission-control.md)
    
- [Pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)
    
- [Pianificare il bypass multimediale in Skype for Business](media-bypass.md)
    
- [Pianificare le linee telefoniche private con Skype for Business](private-telephone-lines.md)
    
- [Pianificare il routing Location-Based in Skype for Business](location-based-routing.md)
    
- [Pianificare le funzionalità di gestione delle chiamate in Skype for Business](call-management-features.md)
    
- [Pianificare la VoIP aziendale resilienza in Skype for Business Server](enterprise-voice-resiliency.md)
    

