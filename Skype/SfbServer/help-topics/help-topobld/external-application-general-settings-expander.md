---
title: Espansione delle impostazioni generali delle applicazioni esterne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Per modificare le proprietà di un server delle applicazioni attendibile già definito, seguire queste istruzioni.
ms.openlocfilehash: 99ccca72613edbde4b38d21dd8e8bb121e5a8dd5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697361"
---
# <a name="external-application-general-settings-expander"></a>Espansione delle impostazioni generali delle applicazioni esterne
 
Per modificare le proprietà di un server delle applicazioni attendibile già definito, seguire queste istruzioni.
  
È possibile modificare due sezioni:
  
> Impostazioni generali
> 
> Impostazioni dell'hop successivo
    
## <a name="general-settings"></a>Impostazioni generali

È possibile modificare il nome di dominio completo corrente per il pool di server applicazioni attendibili. Modificare il nome dell'FQDN del pool. È necessario che i record DNS (Domain Name System) host (A) siano presenti per la nuova voce prima che i client o i server possano connettersi al nuovo nome del pool.
  
Selezionare **Abilita la replica dei dati di configurazione nel pool** se è necessario avere la replica dei dati di configurazione nel pool. Deselezionare il segno di spunta se non si vogliono replicare i dati di configurazione.
  
## <a name="next-hop-settings"></a>Impostazioni hop successivo

È possibile specificare il server dell'hop successivo del pool di server delle applicazioni attendibili selezionando il pool di front end di Enterprise Edition definito o il server front-end Standard Edition nell'elenco a discesa. Un pool di Director o Director non è una selezione valida per un server applicazioni attendibile hop successivo e non verrà visualizzato nell'elenco.
  


Fare clic su **OK** per accettare e salvare le modifiche. Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.
  

