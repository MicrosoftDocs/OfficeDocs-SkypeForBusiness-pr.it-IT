---
title: Strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Lo strumento di stress e prestazioni di Skype for Business Server 2015 viene usato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195075"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Strumento di stress e prestazioni di Skype for Business Server 2015
 
Lo strumento di stress e prestazioni di Skype for Business Server 2015 viene usato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
  
Lo strumento di stress e prestazioni di Skype for Business Server 2015 include strumenti che faciliteranno la pianificazione della capacità per Skype for Business Server 2015. Lo strumento di stress e prestazioni di Skype for Business Server 2015 ti aiuterà a:
  
- Semplificare la pianificazione hardware per Skype for Business Server
    
- Offrire maggiori informazioni e procedure consigliate per l'ottimizzazione delle prestazioni
    
- Misurare le prestazioni delle distribuzioni di Skype for Business Server
    
In genere si usa questo strumento dopo aver usato lo [strumento di pianificazione di Skype for Business server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e perfezionare la topologia con il [calcolatore di pianificazione della capacità di Skype for Business Server 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Questo strumento non verrà aggiornato per Skype for Business Server 2019.
  
## <a name="tests"></a>Test

Lo strumento di stress e prestazioni può simulare questi tipi di caricamento degli utenti:
  
|||
|:-----|:-----|
|Messaggistica istantanea (IM) e presenza  <br/> |Audioconferenza  <br/> |
|Condivisione applicazioni  <br/> |Voice over IP (VoIP), inclusa la simulazione PTSN (Public Switched Telephone Network)  <br/> |
|Servizi di conferenza client di Web Access  <br/> |Operatore automatico conferenza  <br/> |
|Response Group  <br/> |Espansione della lista di distribuzione  <br/> |
|Query di download e Rubrica per la Rubrica  <br/> |Chiamate avanzate di 911 (E911) e profilo posizione (dial plan)  <br/> |
|MultiView  <br/> |Collaborazione dati  <br/> |
|Mobilità  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applicazioni e file inclusi nello strumento per lo stress e le prestazioni di Skype for Business Server 2015

Queste applicazioni fanno parte dello strumento di stress e prestazioni di Skype for Business Server:
  
|**Strumento**|**Descrizione**|
|:-----|:-----|
|UserProvisioningTool. exe  <br/> |Questo strumento viene usato per creare utenti e contatti.  <br/> |
|UserProfileGenerator. exe  <br/> |Consente di configurare le caratteristiche del carico utente che si sta simulando.  <br/> |
|LyncPerfTool. exe  <br/> |Strumento che simula il caricamento dell'utente.  <br/> |
|Default. TMX  <br/> |Necessario per usare lo strumento di registrazione di Skype for Business Server 2015.  <br/> |
|Esempi di script di provisioning  <br/> |Consente di configurare la topologia per l'utilizzo di test di carico, in base a scenari specifici. È probabile che sia necessario modificarle per renderle rilevanti per l'ambiente specifico.  <br/> |
   
## <a name="topics-in-this-section"></a>Argomenti in questa sezione

Per altre informazioni, vedere gli articoli seguenti:
  
- [Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines](prerequisites-and-setup.md)
    
- [Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015](scenarios.md)
    
  - [Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni](provisioning-the-topology-to-run-load.md)
    
  - [Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015](configuring-policies.md)
    
- [Uso dello strumento di stress e prestazioni di Skype for Business Server 2015](using-the-tool.md)
    
- [Domande frequenti per lo strumento di stress e prestazioni di Skype for Business Server 2015](faq.md)
    

