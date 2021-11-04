---
title: Espansione delle impostazioni del servizio Controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.
ms.openlocfilehash: 43e5fe0926c94977c2d19a7e5deccf83cb914799
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752375"
---
# <a name="call-admission-control-settings-expander"></a>Espansione delle impostazioni del servizio Controllo di ammissione di chiamata
 
Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda. 
  
> [!NOTE]
> È inoltre possibile utilizzare il Pannello di controllo o i cmdlet della shell di gestione per abilitare il controllo di ammissione di chiamata. 
  
Nella sezione **Impostazione controllo di ammissione di chiamata** della finestra di dialogo **Modifica proprietà** per il sito è possibile modificare le impostazioni seguenti:
  
- **Abilita Controllo di ammissione di chiamata** Selezionare questa impostazione per abilitare il controllo di ammissione di chiamata. Deselezionare questa impostazione per disabilitare tale servizio per l'intera rete. Per poter abilitare il controllo di ammissione di chiamata, è necessario avere configurato la rete per il servizio. Per informazioni dettagliate, vedere [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) nella documentazione relativa alla distribuzione.
    
- **Pool Front End per l'esecuzione di Controllo di ammissione di chiamata** Se è stato abilitato il controllo di ammissione di chiamata, è possibile modificare il pool che lo esegue. A tale scopo, selezionare il pool desiderato nell'elenco a discesa.
    

