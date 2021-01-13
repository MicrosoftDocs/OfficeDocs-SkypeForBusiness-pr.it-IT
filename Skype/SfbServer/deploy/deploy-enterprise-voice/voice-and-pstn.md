---
title: Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Riepilogo: informazioni su come configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for Business Server.'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830446"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Skype for business
 
**Riepilogo:** Informazioni su come configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for Business Server.
  
I criteri vocali, i record di utilizzo PSTN e le route vocali sono strettamente correlati. È infatti possibile configurare i criteri vocali selezionando un insieme di funzionalità di chiamata e quindi assegnando al criterio un insieme di record di utilizzo PSTN, che specificano quali diritti sono autorizzati per gli utenti o i gruppi a cui viene assegnato il criterio. Anche alle route vocali vengono assegnati record di utilizzo PSTN, allo scopo di trovare una corrispondenza tra le route e gli utenti che sono autorizzati a utilizzarle. In altri termini, gli utenti possono effettuare esclusivamente chiamate che utilizzino le route per cui dispongono di un record di utilizzo PSTN corrispondente.
  
Il flusso di lavoro consigliato per una nuova distribuzione di VoIP aziendale consiste nel configurare innanzitutto un criterio vocale contenente i record di utilizzo PSTN appropriati e quindi nell'associare le route appropriate a ogni record di utilizzo PSTN. 
  
> [!NOTE]
> È inoltre possibile creare criteri vocali con ambito  *utente*  e assegnarli a singoli utenti o gruppi.
  
Per i passaggi dettagliati per l'esecuzione di ognuna di queste attività, vedere le procedure descritte in questa sezione.
  
## <a name="in-this-section"></a>Contenuto della sezione

- [Creare o modificare criteri vocali e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)
    
- [Configurare l'escape della posta vocale in Skype for business](configure-voice-mail-escape.md)
    
- [Visualizzare i record di utilizzo PSTN in Skype for business](view-pstn-usage-records.md)
    
- [Creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md)
    
- [Esportare o importare un file di configurazione di route vocali in Skype for business](voice-route-configuration-import-export.md)
    
- [Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md)
    

