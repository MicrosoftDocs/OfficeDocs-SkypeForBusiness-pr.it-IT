---
title: Expander impostazioni generali applicazioni esterne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà di un server delle applicazioni attendibile già definito, seguire queste istruzioni.
ms.openlocfilehash: 96118d968a5c9fdf54a78df24019426e562220dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194337"
---
# <a name="external-application-general-settings-expander"></a>Expander impostazioni generali applicazioni esterne
 
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
  

