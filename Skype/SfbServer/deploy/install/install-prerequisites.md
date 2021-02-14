---
title: Installare i prerequisiti per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: "Riepilogo: informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801716"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installare i prerequisiti per Skype for Business Server
 
**Riepilogo:** Informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal [Centro di valutazione Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
L'installazione dei prerequisiti consiste nella configurazione di Windows Server mediante l'installazione dei ruoli e delle funzionalità necessari in ognuno dei server della topologia. I requisiti si basano sul ruolo che il server adempirà nella topologia. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. L'installazione dei prerequisiti è il passaggio 1 di 8.
  
![Diagramma di panoramica - Prerequisiti per l'installazione.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Installazione di Windows Server

Skype for Business Server richiede il sistema operativo Windows Server e alcuni prerequisiti prima di poter essere installato. Per informazioni dettagliate sulla pianificazione dei prerequisiti, vedere [Requisiti server per Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> Questa procedura utilizza Windows Server 2012 R2. Se si utilizza una versione diversa di Windows Server, la procedura potrebbe essere leggermente diversa. 
  
> [!IMPORTANT]
> Prima di iniziare, assicurati che Windows Server sia aggiornato tramite Windows Update. 
  
![Windows Server aggiornato.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Guardare i passaggi video per **installare i prerequisiti:**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installare i ruoli e le funzionalità necessari per i server front-end

È possibile installare i ruoli e le funzionalità necessari utilizzando Server Manager. 
    
1. Installare le funzionalità software prerequisiti elencate in [Requisiti server per Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) Il software necessario deve essere nel server che eseguirà Skype for Business Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 non installa tutti i file di origine per le funzionalità necessarie per impostazione predefinita. Se il server non è connesso a Internet, sarà necessario inserire il supporto di  Windows Server 2012 R2 e selezionare Specificare un percorso di origine alternativo per installare le funzionalità necessarie. I file di origine si trovano nella directory sources\sxs. Ad esempio, se il supporto di Windows Server 2012 R2 si trova nell'unità D, è necessario impostare il percorso su `d:\sources\sxs` . È importante disporre degli aggiornamenti più recenti di Windows Update. Se non si è connessi a Internet, sarà necessario installare manualmente tutti gli aggiornamenti rilevanti e tutti i prerequisiti per gli aggiornamenti necessari. 
  
1. Quando la finestra di dialogo indica che l'installazione è stata completata, sarà necessario riavviare il server per completare il processo.
    
1. Eseguire **di nuovo Windows Update** per verificare se sono presenti aggiornamenti dei ruoli e dei servizi installati.
    
1. Se si utilizza il Pannello di controllo di Skype for Business Server su questo server, è necessario installare anche Silverlight. Per installare Silverlight, vedere [Microsoft Silverlight.](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> I prerequisiti per i server che eseguono ruoli diversi dal server front-end, ad esempio il ruolo di Director, Persistent Chat o Edge, hanno i propri prerequisiti. Per informazioni dettagliate sui prerequisiti esatti richiesti da ogni tipo di server, vedere [Requisiti del server per Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) 
  

