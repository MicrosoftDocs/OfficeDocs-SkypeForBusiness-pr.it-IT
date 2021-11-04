---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Lo Skype for Business Server 2015 Stress and Performance Tool viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
ms.openlocfilehash: 565f868ae81915b6bcb595f13c2d184d82db62b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766264"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Lo Skype for Business Server 2015 Stress and Performance Tool viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
  
Lo Skype for Business Server 2015 Stress and Performance Tool include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2015. Lo Skype for Business Server 2015 Stress and Performance Tool consente di:
  
- Semplificare la pianificazione dell'hardware per Skype for Business Server
    
- Fornire maggiori conoscenze e procedure consigliate per l'ottimizzazione delle prestazioni
    
- Misurare le prestazioni delle Skype for Business Server distribuzione
    
Questo strumento viene in genere utilizzato dopo aver utilizzato lo Strumento di pianificazione di [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e perfezionando la topologia con lo strumento di calcolo della pianificazione della capacità di [Skype for Business Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Questo strumento non verrà aggiornato per Skype for Business Server 2019.
  
## <a name="tests"></a>Test

Lo strumento Stress and Performance può simulare questi tipi di carico utente:
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Messaggistica istantanea e presenza   |Audioconferenza   |
|Condivisione applicazioni   |Voice over IP (VoIP), inclusa la simulazione PTSN (Public Switched Telephone Network)   |
|Web Access Client Conferencing   |Operatore automatico conferenza   |
|Response Group   |Espansione delle liste di distribuzione   |
|Download della rubrica e query della rubrica   |Chiamate 911 (E911) avanzate e profilo località (dial plan)   |
|MultiView   |Collaborazione dati   |
|Mobilità   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applicazioni e file inclusi con lo Skype for Business Server 2015 Stress and Performance Tool

Queste applicazioni fanno parte dello strumento Skype for Business Server stress e prestazioni:
  
|Strumento|Descrizione|
|:-----|:-----|
|UserProvisioningTool.exe   |Questo strumento viene utilizzato per creare utenti e contatti.   |
|UserProfileGenerator.exe   |Usato per configurare le caratteristiche del carico utente che si sta simulando.   |
|LyncPerfTool.exe   |Strumento che simula il carico utente.   |
|Default.tmx   |Necessario per utilizzare lo strumento di Skype for Business Server 2015.   |
|Esempi di script di provisioning   |Utilizzato per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici. È probabile che sia necessario modificarli per renderli rilevanti per il proprio ambiente specifico.   |
   
## <a name="topics-in-this-section"></a>Argomenti di questa sezione

Per saperne di più, consultare gli articoli seguenti:
  
- [Prerequisiti e configurazione per lo strumento Skype per Busines Stress and Performance Tool](prerequisites-and-setup.md)
    
- [Scenari di prestazioni per lo Skype for Business Server 2015 Stress and Performance Tool](scenarios.md)
    
  - [Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni](provisioning-the-topology-to-run-load.md)
    
  - [Configurazione dei criteri per lo Skype for Business Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [Utilizzo dello strumento Skype for Business Server 2015 Stress and Performance](using-the-tool.md)
    
- [Domande frequenti per lo Skype for Business Server 2015 Stress and Performance Tool](faq.md)
    

