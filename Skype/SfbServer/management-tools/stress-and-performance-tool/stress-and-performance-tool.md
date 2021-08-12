---
title: Skype for Business Server 2015 Stress and Performance Tool
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
description: Lo Skype for Business Server 2015 Stress and Performance Tool viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
ms.openlocfilehash: 1dff13905145752c57b02795e9aab07737d51b33d94d6355ce5f8c55fa62e7ea
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328021"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Lo Skype for Business Server 2015 Stress and Performance Tool viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
  
Lo Skype for Business Server 2015 Stress and Performance Tool include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2015. Lo Skype for Business Server 2015 Stress and Performance Tool consente di:
  
- Semplificare la pianificazione dell'hardware per Skype for Business Server
    
- Fornire maggiori conoscenze e procedure consigliate per l'ottimizzazione delle prestazioni
    
- Misurare le prestazioni delle Skype for Business Server distribuzione
    
Questo strumento viene in genere utilizzato dopo aver utilizzato lo strumento di pianificazione di [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e aver perfezionato la topologia con lo strumento di calcolo della pianificazione della capacità di [Skype for Business Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Questo strumento non verrà aggiornato per Skype for Business Server 2019.
  
## <a name="tests"></a>Test

Lo strumento Stress and Performance può simulare questi tipi di carico utente:
  
|||
|:-----|:-----|
|Messaggistica istantanea e presenza  <br/> |Audioconferenza  <br/> |
|Condivisione applicazioni  <br/> |Voice over IP (VoIP), inclusa la simulazione PTSN (Public Switched Telephone Network)  <br/> |
|Web Access Client Conferencing  <br/> |Operatore automatico conferenza  <br/> |
|Response Group  <br/> |Espansione delle liste di distribuzione  <br/> |
|Download della rubrica e query della rubrica  <br/> |Chiamate enhanced 911 (E911) e profilo località (dial plan)  <br/> |
|MultiView  <br/> |Collaborazione dati  <br/> |
|Mobilità  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applicazioni e file inclusi con lo Skype for Business Server 2015 Stress and Performance Tool

Queste applicazioni fanno parte dello strumento Skype for Business Server stress e prestazioni:
  
|**Strumento**|**Descrizione**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Questo strumento viene utilizzato per creare utenti e contatti.  <br/> |
|UserProfileGenerator.exe  <br/> |Usato per configurare le caratteristiche del carico utente che si sta simulando.  <br/> |
|LyncPerfTool.exe  <br/> |Strumento che simula il carico utente.  <br/> |
|Default.tmx  <br/> |Necessario per utilizzare lo strumento di Skype for Business Server 2015.  <br/> |
|Esempi di script di provisioning  <br/> |Utilizzato per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici. È probabile che sia necessario modificarli per renderli rilevanti per il proprio ambiente specifico.  <br/> |
   
## <a name="topics-in-this-section"></a>Argomenti di questa sezione

Per saperne di più, consultare gli articoli seguenti:
  
- [Prerequisiti e configurazione per lo strumento Skype per Busines Stress and Performance Tool](prerequisites-and-setup.md)
    
- [Scenari di prestazioni per lo Skype for Business Server 2015 Stress and Performance Tool](scenarios.md)
    
  - [Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni](provisioning-the-topology-to-run-load.md)
    
  - [Configurazione dei criteri per lo strumento Skype for Business Server 2015 Stress and Performance](configuring-policies.md)
    
- [Utilizzo dello Skype for Business Server 2015 Stress and Performance Tool](using-the-tool.md)
    
- [Domande frequenti per lo Skype for Business Server 2015 Stress and Performance Tool](faq.md)
    

