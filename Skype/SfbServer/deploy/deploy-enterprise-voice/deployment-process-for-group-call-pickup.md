---
title: Processo di distribuzione per il ritiro delle chiamate di gruppo in Skype for business
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
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processo di distribuzione e passaggi per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 5c89522828e5e5a0dc04ffccb0907c0a2cb8a008
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812346"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processo di distribuzione per il ritiro delle chiamate di gruppo in Skype for business
 
Processo di distribuzione e passaggi per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale.
  
Il prelievo delle chiamate di gruppo consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi tramite i propri telefoni. 
  
 Quando si distribuisce VoIP aziendale, i componenti utilizzati dal prelievo di chiamata di gruppo vengono installati e abilitati automaticamente nel front end server o nel server Standard Edition. Tuttavia, è necessario eseguire la procedura seguente per configurare il prelievo delle chiamate di gruppo prima che sia disponibile per gli utenti.
  
**Processo di distribuzione del prelievo delle chiamate di gruppo**

|**Fase**|**Procedura**|**Gruppi e ruoli obbligatori**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Abilitare lo strumento SEFAUtil nella topologia|Utilizzare il cmdlet New-CsTrustedApplicationPool per creare un nuovo pool di applicazioni attendibili. Utilizzare il cmdlet New-CsTrustedApplication per specificare lo strumento SEFAUtil come applicazione attendibile. Eseguire il cmdlet Enable-CsTopology per abilitare la topologia. Se non è già presente, scaricare la versione di Skype for Business Server dello strumento SEFAUtil da questo percorso e installarla nel pool di applicazioni attendibili creato nel passaggio 1. Verificare che SEFAUtil sia in esecuzione correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione. |RTCUniversalServerAdmins  <br/> |[Distribuire lo strumento SEFAUtil in Skype for business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015](../../management-tools/resource-kit-tools.md). (Per Skype for Business Server è necessario utilizzare la versione corrente dello strumento, ma è ancora applicabile la documentazione di Lync Server 2013).  <br/> |
|Configurare gli intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata  <br/> |Utilizzare il cmdlet **New-CsCallParkOrbit** per creare intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata e assegnare gli intervalli di prelievo delle chiamate di tipo **GroupPickup**.  <br/> Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri vengono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di intervallo nella tabella orbit del parcheggio di chiamata non è supportata.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Skype for business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il prelievo delle chiamate di gruppo per gli utenti  <br/> |Utilizzare il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il prelievo delle chiamate di gruppo e assegnare un numero di prelievo di chiamata per gli utenti.  <br/> |-  <br/> |[Abilitazione del prelievo delle chiamate di gruppo per gli utenti e assegnazione di un numero di gruppo in Skype for business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificare agli utenti il numero di prelievo di chiamata assegnato e qualsiasi altro numero di interesse  <br/> |Dopo aver abilitato il ritiro delle chiamate di gruppo per gli utenti, utilizzare la posta elettronica o un altro meccanismo per notificare agli utenti il numero del gruppo di prelievo delle chiamate. Notificare agli utenti il numero del gruppo di prelievo delle chiamate per qualsiasi gruppo che potrebbe voler monitorare. Poiché gli utenti possono recuperare le chiamate per gli altri utenti anche se non sono nello stesso gruppo, gli utenti potrebbero richiedere il numero del gruppo di prelievo delle chiamate per più gruppi.  <br/> |-  <br/> ||
|Verificare la distribuzione del prelievo delle chiamate di gruppo  <br/> | Provare a inserire e recuperare le chiamate per assicurarsi che la configurazione funzioni come previsto. Verificare almeno quanto segue: <br/>  Chiamare un utente abilitato per il prelievo delle chiamate di gruppo e richiedere a un altro utente di recuperare la chiamata. L'altro utente può trovarsi nello stesso gruppo, in un gruppo diverso o non è abilitato per il prelievo delle chiamate di gruppo. <br/>  Chiamare un utente abilitato per il prelievo delle chiamate di gruppo e non rispondere alla chiamata. <br/> |-  <br/> ||
   

