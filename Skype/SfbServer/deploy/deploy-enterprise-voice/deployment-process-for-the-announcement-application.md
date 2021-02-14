---
title: Processo di distribuzione per l'applicazione Annuncio in Skype for Business Server
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo di distribuzione e passaggi per l'applicazione Annuncio in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812306"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processo di distribuzione per l'applicazione Annuncio in Skype for Business Server
 
Processo di distribuzione e passaggi per l'applicazione Annuncio in Skype for Business Server VoIP aziendale.
  
L'applicazione Annuncio è una funzionalità di VoIP aziendale che consente di configurare cosa accade alle chiamate a estensioni non assegnate (estensioni valide per l'organizzazione, ma non assegnate a una persona o a un telefono). È ad esempio possibile configurare le chiamate a numeri non assegnati in modo che venga riprodotto un messaggio, in modo che vengano trasferite a un'altra destinazione oppure in modo che vengano eseguite entrambe queste azioni.
  
L'applicazione Annuncio viene installata come caratteristica dell'applicazione Response Group nel Front End Server o nel server Standard Edition quando si distribuisce VoIP aziendale. È necessario configurare gli annunci caricando i file audio oppure configurando la sintesi vocale e la tabella dei numeri non assegnati.
  
In questa sezione viene fornita una panoramica dei passaggi necessari per distribuire l'applicazione Annuncio. È necessario distribuire VoIP aziendale prima di configurare gli annunci. I componenti richiesti dall'applicazione Annuncio vengono installati e abilitati quando si distribuisce VoIP aziendale.
  
**Processo di distribuzione degli annunci**

|**Fase**|**Procedura**|**Ruoli**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurazione delle impostazioni degli annunci  <br/> | Creare l'annuncio registrando e caricando file audio o tramite sintesi vocale. <br/>  Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli all'annuncio appropriato. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Creare o eliminare un annuncio in Skype for Business Server](create-an-announcement.md) <br/> [Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Verifica della distribuzione degli annunci  <br/> |Testare ascoltando annunci per verificare che la configurazione funzioni nel modo previsto.  <br/> |-  <br/> |[(Facoltativo) Verificare la distribuzione degli annunci in Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

