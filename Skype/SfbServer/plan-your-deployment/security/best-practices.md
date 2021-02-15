---
title: Procedure consigliate per l'infrastruttura di base in Skype for Business Server
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
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: È probabile che siano già state intraprese azioni per progettare la tolleranza di errore nel sistema, ad esempio garantendo la ridondanza hardware, prendendo precauzioni in caso di interruzioni dell'alimentazione, installando con regolarità gli aggiornamenti antivirus e della sicurezza e monitorando l'attività dei server. Queste procedure sono vantaggiose non solo dell'infrastruttura di Skype for Business Server, ma anche dell'intera rete. Se queste procedure non sono state implementate, è consigliabile farlo prima di distribuire Skype for Business Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832246"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedure consigliate per l'infrastruttura di base in Skype for Business Server
 
È probabile che siano già state intraprese azioni per progettare la tolleranza di errore nel sistema, ad esempio garantendo la ridondanza hardware, prendendo precauzioni in caso di interruzioni dell'alimentazione, installando con regolarità gli aggiornamenti antivirus e della sicurezza e monitorando l'attività dei server. Queste procedure sono vantaggiose non solo dell'infrastruttura di Skype for Business Server, ma anche dell'intera rete. Se queste procedure non sono state implementate, è consigliabile farlo prima di distribuire Skype for Business Server.
  
Per proteggere i server nella distribuzione di Skype for Business Server da danni accidentali o intenzionali che potrebbero causare tempi di inattività, adottare le precauzioni seguenti:
  
- Installare con regolarità gli aggiornamenti della sicurezza nei server. Sottoscrivendo il servizio Microsoft Security Notification Service, è possibile ricevere una notifica immediata ogni volta che vengono pubblicati bollettini sulla sicurezza per i prodotti Microsoft. Per effettuare la sottoscrizione, accedere al sito [Web Delle notifiche sulla sicurezza tecnica Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=145202)
    
- Verificare che i diritti di accesso siano configurati correttamente.
    
- Posizionare i server in un ambiente fisico con accesso consentito soltanto a personale autorizzato. Verificare che in tutti i server sia installato il software antivirus appropriato. Mantenere il software aggiornato con i file delle impronte digitali dei virus più recenti. Utilizzare la funzionalità di aggiornamento automatico dell'applicazione antivirus per mantenere costantemente aggiornate le impronte digitali dei virus.
    
- È consigliabile disabilitare i servizi del sistema operativo Windows Server non necessari nei computer in cui si installa Skype for Business Server.
    
- Crittografare i sistemi operativi e le unità disco in cui sono archiviati i dati con un sistema di crittografia dell'intero volume, a meno che non sia possibile garantire il controllo completo e costante dei server, l'isolamento fisico totale e la rimozione delle autorizzazioni appropriata e sicura per le unità disco sostituite o guaste.
    
- Disabilitare tutte le porte DMA (Direct Memory Access) esterne del server, a meno che non sia possibile garantire un controllo rigoroso dell'accesso fisico ai server. Gli attacchi basati su DMA, che possono essere eseguiti piuttosto facilmente, rendono vulnerabili le informazioni riservate, ad esempio le chiavi di crittografia private.
    

