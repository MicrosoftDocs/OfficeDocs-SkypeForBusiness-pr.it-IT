---
title: Pianificare VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Nozioni di base sulla pianificazione di VoIP aziendale in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico di utilizzo vocale.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825676"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Pianificare VoIP aziendale in Skype for Business Server
 
Nozioni di base sulla pianificazione di VoIP aziendale in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico di utilizzo vocale.
  
Il processo di distribuzione per VoIP aziendale dipende dalla topologia esistente, dall'infrastruttura e dalla funzionalità VoIP aziendale che si desidera supportare. Le procedure necessarie dipenderanno dalle funzionalità scelte, ma è necessario tenere conto di altre considerazioni sulla pianificazione a livello superiore.
  
In generale, prendere in considerazione il tipo e il numero di siti che si desidera distribuire e le relative posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che connettono i siti, se si desidera fornire ridondanza e failover per le funzionalità vocali per ogni sito e se si desidera utilizzare apparecchiature PBX esistenti. Sono presenti alcune considerazioni, ad esempio la disponibilità elevata, che è opportuno considerare quando si pianifica di utilizzare Skype for Business Server nel suo complesso. Queste considerazioni sono descritte negli argomenti in questa sezione, in base alle esigenze.
  
## <a name="sites-and-regions"></a>Siti e aree geografiche

In primo luogo, identificare i siti nella topologia in cui verranno distribuiti Enterprise Voice e le aree di rete a cui appartengono tali siti. Valutare in particolare il modo in cui verrà fornita la connettività PSTN (Public Switched Telephone Network) a ogni sito. Per motivi logistici e di gestione, le aree a cui appartengono questi siti possono rappresentare un fattore decisivo. Decidere dove verranno distribuiti i gateway localmente, in cui verrà distribuito Survivable Branch Appliance (SBA) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) a un provider di servizi di telefonia Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Collegamenti di rete tra siti

È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale. Se si dispone o si pianifica la distribuzione dei collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per fornire la terminazione DID (Direct inwards) locale per gli utenti di tali siti. Se si dispone di collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il servizio Controllo di ammissione di chiamata per il collegamento. Se non si dispone di collegamenti WAN resilienti, ospitare meno di 1000 utenti nel sito di succursale e non sono disponibili amministratori di Skype for Business Server addestrati localmente, è consigliabile distribuire un Survivable Branch Appliance nel sito di succursale. Se si dispone di un host compreso tra 1000 e 5000 utenti nel sito di succursale, manca una connessione WAN resiliente e sono disponibili amministratori di Skype for Business Server addestrati, è consigliabile distribuire un Survivable Branch Server con un gateway di piccole dimensioni nel sito di succursale. Prendere inoltre in considerazione l'eventualità di abilitare il bypass multimediale nei collegamenti vincolati se si dispone di un peer gateway che supporta il bypass multimediale.
  
## <a name="estimating-voice-usage-and-traffic"></a>Stima dell'utilizzo e del traffico vocale

Microsoft Lync Server 2013, strumento di pianificazione utilizza la metrica seguente per valutare il traffico degli utenti in ogni sito e il numero di porte necessarie per il supporto del traffico.
  
> Per un livello di **traffico leggero** (una chiamata PSTN per utente all'ora) considerare 15 utenti per porta.
> 
> Per un livello di **traffico medio** (2 chiamate PSTN per utente all'ora) considerare 10 utenti per porta.
> 
> Per un livello di **traffico pesante** (3 chiamate PSTN o più per utente all'ora) considerare 5 utenti per porta.
    
Il numero di porte determina il numero di Mediation Server e gateway necessari. I gateway PSTN (Public Switched Telephone Network) distribuiti nella maggior parte delle organizzazioni variano in dimensione da 2 a 960 porte. Sono disponibili anche gateway più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia.
  
Un'organizzazione con 10.000 utenti e traffico medio, ad esempio, necessiterebbe di 1000 porte. Il numero di gateway richiesti sarebbe uguale al numero totale di porte necessarie determinato in base alla capacità totale dei gateway.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componenti, funzionalità e opzioni di VoIP aziendale

Per ulteriori informazioni sulla pianificazione della distribuzione di VoIP aziendale, vedere le sezioni seguenti.
  
- [Componenti necessari per VoIP aziendale in Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Pianificare la connettività PSTN in Skype for Business Server](pstn-connectivity-0.md)
    
- [Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Pianificare il controllo di ammissione di chiamata in Skype for Business Server](call-admission-control.md)
    
- [Pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)
    
- [Pianificare il bypass multimediale in Skype for business](media-bypass.md)
    
- [Pianificare le linee telefoniche private con Skype for business](private-telephone-lines.md)
    
- [Pianificare Location-Based routing in Skype for business](location-based-routing.md)
    
- [Pianificare le funzionalità di gestione delle chiamate in Skype for business](call-management-features.md)
    
- [Pianificare la resilienza di VoIP aziendale in Skype for Business Server](enterprise-voice-resiliency.md)
    

