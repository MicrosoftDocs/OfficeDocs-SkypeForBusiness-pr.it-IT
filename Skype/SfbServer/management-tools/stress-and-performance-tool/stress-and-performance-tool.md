---
title: Strumento per lo stress e le prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di testing.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814926"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Strumento per lo stress e le prestazioni di Skype for Business Server 2015
 
Lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di testing.
  
Lo strumento per lo stress e le prestazioni di Skype for Business Server 2015 include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2015. Lo strumento di supporto per la sollecitazione e le prestazioni di Skype for Business Server 2015 consente di:
  
- Semplificare la pianificazione dell'hardware per Skype for Business Server
    
- Offrire maggiori informazioni e procedure consigliate per l'ottimizzazione delle prestazioni
    
- Misurare le prestazioni delle distribuzioni di Skype for Business Server
    
Questo strumento viene in genere utilizzato dopo aver utilizzato lo [strumento di pianificazione di Skype for Business server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e perfezionare la topologia con il [calcolatore di pianificazione della capacità di Skype for Business Server 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Questo strumento non verrà aggiornato per Skype for Business Server 2019.
  
## <a name="tests"></a>Test

Lo strumento stress and performance è in grado di simulare questi tipi di carico utente:
  
|||
|:-----|:-----|
|Messaggistica istantanea (IM) e presenza  <br/> |Audioconferenza  <br/> |
|Condivisione applicazioni  <br/> |VoIP (Voice over IP), inclusa la simulazione PTSN (Public Switched Telephone Network)  <br/> |
|Servizi di conferenza client di accesso Web  <br/> |Operatore automatico conferenza  <br/> |
|Response Group  <br/> |Espansione della lista di distribuzione  <br/> |
|Download della Rubrica e query della Rubrica  <br/> |Chiamate e profili delle posizioni migliorati di 911 (E911) (dial plan)  <br/> |
|MultiView  <br/> |Collaborazione dati  <br/> |
|Mobilità  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applicazioni e file forniti con lo strumento di stress e prestazioni di Skype for Business Server 2015

Queste applicazioni fanno parte dello strumento per lo stress e le prestazioni di Skype for Business Server:
  
|**Strumento**|**Descrizione**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Questo strumento viene utilizzato per creare utenti e contatti.  <br/> |
|UserProfileGenerator.exe  <br/> |Utilizzato per configurare le caratteristiche del carico utente che si sta simulando.  <br/> |
|LyncPerfTool.exe  <br/> |Strumento che simula il caricamento dell'utente.  <br/> |
|Default. TMX  <br/> |Necessario per utilizzare lo strumento di registrazione di Skype for Business Server 2015.  <br/> |
|Esempi di script di provisioning  <br/> |Utilizzato per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici. È probabile che sia necessario modificarli per renderli rilevanti per l'ambiente specifico.  <br/> |
   
## <a name="topics-in-this-section"></a>Argomenti in questa sezione

Per ulteriori informazioni, vedere gli articoli seguenti:
  
- [Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines](prerequisites-and-setup.md)
    
- [Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015](scenarios.md)
    
  - [Provisioning della topologia per l'esecuzione del carico negli scenari di stress e prestazioni](provisioning-the-topology-to-run-load.md)
    
  - [Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015](configuring-policies.md)
    
- [Utilizzo dello strumento di sollecito e prestazioni di Skype for Business Server 2015](using-the-tool.md)
    
- [Domande frequenti sullo strumento di stress e prestazioni di Skype for Business Server 2015](faq.md)
    

