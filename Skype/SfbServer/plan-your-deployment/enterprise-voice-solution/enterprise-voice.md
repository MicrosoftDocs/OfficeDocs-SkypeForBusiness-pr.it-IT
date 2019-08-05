---
title: Pianificare VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Nozioni di base su Enterprise Voice Planning in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico per uso vocale.
ms.openlocfilehash: fdc653404f6b7182086af00e6e788a1d3bd421eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187694"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Pianificare VoIP aziendale in Skype for Business Server
 
Nozioni di base su Enterprise Voice Planning in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico per uso vocale.
  
Il processo di distribuzione per VoIP aziendale dipende dalla topologia, dall'infrastruttura e dalla funzionalità di VoIP aziendale che si vuole supportare. Le procedure necessarie dipendono dalle caratteristiche scelte, ma esistono altre considerazioni di pianificazione che è necessario apportare a un livello elevato.
  
In generale, prendere in considerazione il tipo e il numero di siti che si desidera distribuire e le rispettive posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che collegano i siti, se si vuole ottenere la ridondanza e il failover per le funzionalità vocali per ogni sito e se si vuole usare apparecchiature PBX esistenti. Ci sono alcune considerazioni, ad esempio l'elevata disponibilità, da tenere in considerazione quando si prevede di usare Skype for Business Server nel suo complesso. Queste considerazioni sono discusse in argomenti in questa sezione, in base alle esigenze.
  
## <a name="sites-and-regions"></a>Siti e aree geografiche

Prima di tutto, identificare i siti della topologia in cui distribuire VoIP aziendale e le aree di rete a cui appartengono tali siti. In particolare, valutare come si fornirà la connettività PSTN (Public Switched Telephone Network) a ogni sito. Per motivi di gestibilità e logistica, le aree geografiche a cui appartengono questi siti possono essere un fattore decisivo. Decidere dove verranno distribuiti i gateway localmente, dove saranno distribuiti gli appliance Survivable Branch (SBAs) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) in un provider di servizi di telefonia Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Collegamenti di rete tra siti

È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale. Se si ha o si prevede di distribuire i collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per specificare la terminazione per gli utenti di tali siti. Se si hanno collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il controllo di ammissione delle chiamate per il collegamento. Se non si dispone di collegamenti WAN resilienti, è necessario ospitare meno di 1000 utenti nel sito della filiale e non sono disponibili amministratori locali addestrati di Skype for Business Server, è consigliabile distribuire un Survivable Branch Appliance presso il sito della filiale. Se si ospitano tra gli utenti di 1000 e 5000 presso il sito di succursale, non è disponibile una connessione WAN resiliente e sono stati addestrati gli amministratori di Skype for Business Server, è consigliabile distribuire un Survivable Branch Server con un piccolo gateway nel sito della filiale. Se si ha un peer del gateway che supporta il bypass multimediale, è consigliabile anche abilitare il bypass multimediale sui collegamenti vincolati.
  
## <a name="estimating-voice-usage-and-traffic"></a>Stima dell'utilizzo e del traffico vocale

Microsoft Lync Server 2013, strumento di pianificazione usa la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.
  
> Per il **traffico leggero** (una chiamata PSTN per utente per ora), figura 15 utenti per ogni porta.
> 
> Per il **traffico medio** (2 chiamate PSTN per utente per ora), figura 10 utenti per ogni porta.
> 
> Per **traffico intenso** (3 o più chiamate PSTN per utente per ora), figura 5 utenti per ogni porta.
    
Il numero di porte determina a sua volta il numero di server di mediazione e gateway che saranno necessari. I gateway PSTN (Public Switched Telephone Network) che la maggior parte delle organizzazioni considerano la distribuzione di intervalli di dimensioni da 2 porte fino a un numero di porte di 960. Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi di telefonia.
  
Ad esempio, un'organizzazione con gli utenti di 10.000 e il traffico medio richiederebbe porte 1000. Il numero di gateway necessari sarebbe uguale al numero totale di porte richieste come determinato dalla capacità totale dei gateway.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componenti, funzionalità e opzioni di Enterprise Voice

Per altre informazioni sulla pianificazione della distribuzione di VoIP aziendale, vedere le sezioni seguenti.
  
- [Componenti necessari per VoIP aziendale in Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Pianificare la connettività PSTN in Skype for Business Server](pstn-connectivity-0.md)
    
- [Impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](call-admission-control.md)
    
- [Pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)
    
- [Pianificare il bypass multimediale in Skype for business](media-bypass.md)
    
- [Pianificare le linee telefoniche private con Skype for business](private-telephone-lines.md)
    
- [Pianificare il routing basato sulla posizione in Skype for business](location-based-routing.md)
    
- [Pianificare le funzionalità di gestione delle chiamate in Skype for business](call-management-features.md)
    
- [Pianificare la resilienza di VoIP aziendale in Skype for Business Server](enterprise-voice-resiliency.md)
    

