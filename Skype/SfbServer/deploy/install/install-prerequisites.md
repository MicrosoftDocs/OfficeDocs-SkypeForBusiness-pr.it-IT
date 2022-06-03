---
title: Installare i prerequisiti per Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Riepilogo: informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server.'
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860737"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installare i prerequisiti per Skype for Business Server
 
**Riepilogo:** Informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server.
  
L'installazione dei prerequisiti consiste nell'configurare Windows Server installando i ruoli e le funzionalità necessari in ognuno dei server nella topologia. I requisiti sono basati sul ruolo che il server dovrà soddisfare nella topologia. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come descritto nel diagramma. L'installazione dei prerequisiti è il passaggio 1 di 8.
  
![Diagramma di panoramica: prerequisiti di installazione.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurare Windows Server

Skype for Business Server richiede il sistema operativo Windows Server e una serie di prerequisiti prima di poter essere installato. Per informazioni dettagliate sulla pianificazione dei prerequisiti, vedere [Requisiti del server per Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Questa procedura usa Windows Server 2012 R2. Se si usa una versione diversa di Windows Server, la procedura potrebbe essere leggermente diversa. 
  
> [!IMPORTANT]
> Prima di iniziare, assicurarsi che Windows Server sia aggiornato usando Windows Update. 
  
![Windows Server aggiornato.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Guardare i passaggi video per **i prerequisiti di installazione**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installare i ruoli e le funzionalità necessari per i server front-end

È possibile installare i ruoli e le funzionalità necessari usando Server Manager. 
    
1. Installare le funzionalità software dei prerequisiti elencate in [Requisiti del server per Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). Il software necessario deve trovarsi nel server che eseguirà Skype for Business Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 non installa tutti i file di origine per le funzionalità necessarie per impostazione predefinita. Se il server non è connesso a Internet, è necessario inserire il supporto Windows Server 2012 R2 e selezionare **Specifica un percorso di origine alternativo** per installare le funzionalità richieste. I file di origine si trovano nella directory sources\sxs. Ad esempio, se il supporto Windows Server 2012 R2 si trova nell'unità D, impostare il percorso su `d:\sources\sxs`. È importante disporre degli aggiornamenti più recenti di Windows Update. Se non si è connessi a Internet, sarà necessario installare manualmente tutti gli aggiornamenti pertinenti e tutti i prerequisiti per gli aggiornamenti necessari. 
  
1. Quando la finestra di dialogo indica che l'installazione è stata completata, sarà necessario riavviare il server per completare il processo.
    
1. Eseguire **di nuovo Windows Update** per verificare se sono presenti aggiornamenti ai ruoli e ai servizi installati.
    
1. Se si userà Skype for Business Server Pannello di controllo in questo server, è necessario installare anche Silverlight. Per installare Silverlight, vedere [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> I prerequisiti per i server che eseguono ruoli diversi dal server front-end, ad esempio il ruolo di Director, Persistent Chat o Edge, hanno i propri prerequisiti. Per informazioni dettagliate sui prerequisiti esatti richiesti da ogni tipo di server, vedere [Requisiti del server per Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

