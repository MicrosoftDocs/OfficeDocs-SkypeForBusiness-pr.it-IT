---
title: Espansione delle impostazioni del servizio Controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.
ms.openlocfilehash: 4df5a9f5be761e1e039a259d0abf4a38d51170df
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218787"
---
# <a name="call-admission-control-settings-expander"></a>Espansione delle impostazioni del servizio Controllo di ammissione di chiamata
 
Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda. 
  
> [!NOTE]
> È inoltre possibile utilizzare il pannello di controllo o i cmdlet di Management Shell per abilitare il servizio di gestione delle prestazioni. 
  
Nella sezione **Impostazione controllo di ammissione di chiamata** della finestra di dialogo **Modifica proprietà** per il sito è possibile modificare le impostazioni seguenti:
  
- **Abilitazione del controllo di ammissione di chiamata** Selezionare questa impostazione per abilitare il servizio di controllo di ammissione. Deselezionare questa impostazione per disabilitare tale servizio per l'intera rete. Per poter abilitare il controllo di ammissione di chiamata, è necessario avere configurato la rete per il servizio. Per informazioni dettagliate, vedere [deploy Call Admission Control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) nella documentazione relativa alla distribuzione.
    
- **Pool Front end per eseguire il controllo di ammissione di chiamata** Se è stato abilitato il servizio di controllo di ammissione, è possibile modificare il pool che lo esegue. A tale scopo, selezionare il pool desiderato nell'elenco a discesa.
    

