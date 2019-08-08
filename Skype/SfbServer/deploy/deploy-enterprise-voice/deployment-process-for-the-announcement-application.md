---
title: Processo di distribuzione per l'applicazione di annuncio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo di distribuzione e passaggi per l'applicazione di annunci in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 2edb9364408658e9a164210a9fcd5a0196b10da7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245766"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processo di distribuzione per l'applicazione di annuncio in Skype for Business Server
 
Processo di distribuzione e passaggi per l'applicazione di annunci in Skype for Business Server VoIP aziendale.
  
L'applicazione di annuncio è una caratteristica di VoIP aziendale che consente di configurare le chiamate alle estensioni non assegnate (estensioni valide per l'organizzazione, ma non assegnate a una persona o a un telefono). Ad esempio, puoi configurare le chiamate a numeri non assegnati per riprodurre un messaggio o per essere trasferito a una destinazione diversa o entrambe.
  
L'applicazione annuncio viene installata come caratteristica dell'applicazione Response Group nel server front-end o Standard Edition quando si distribuisce VoIP aziendale. È necessario configurare gli annunci caricando i file audio o configurando la sintesi vocale (TTS) e configurando la tabella dei numeri non assegnati.
  
Questa sezione fornisce una panoramica dei passaggi necessari per la distribuzione dell'applicazione di annunci. È necessario distribuire Enterprise Voice prima di configurare gli annunci. I componenti necessari per l'applicazione di annuncio vengono installati e abilitati quando si distribuisce VoIP aziendale.
  
**Processo di distribuzione degli annunci**

|**Fase**|**Passaggi**|**Ruoli**|**Documentazione di distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare le impostazioni degli annunci  <br/> | Creare l'annuncio registrando e caricando i file audio o tramite sintesi vocale. <br/>  Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli con l'annuncio appropriato. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Creare o eliminare un annuncio in Skype for Business Server](create-an-announcement.md) <br/> [Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Verificare la distribuzione degli annunci  <br/> |Eseguire il test ascoltando gli annunci per verificare che la configurazione funzioni come previsto.  <br/> |-  <br/> |[Opzionale Verificare la distribuzione degli annunci in Skype for business](optional-verify-announcement-deployment.md) <br/> |
   

