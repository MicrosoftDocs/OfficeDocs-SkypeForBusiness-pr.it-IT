---
title: Processo di distribuzione per la risposta alle chiamate di gruppo in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processo di distribuzione e passaggi per la risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: bd3f299e8121483cf8a6a7b332c806923a386c66
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601921"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processo di distribuzione per la risposta alle chiamate di gruppo in Skype for Business
 
Processo di distribuzione e passaggi per la risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale.
  
La risposta alle chiamate di gruppo consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi dai propri telefoni. 
  
 I componenti utilizzati dalla risposta alle chiamate di gruppo vengono installati e abilitati automaticamente nel Front End Server o nel server edizione Standard quando si distribuisce VoIP aziendale. Tuttavia, è necessario eseguire la procedura seguente per configurare la risposta alle chiamate di gruppo prima che sia disponibile per gli utenti.
  
**Processo di distribuzione di prelievo chiamata di gruppo**

|**Fase**|**Procedura**|**Gruppi e ruoli obbligatori**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Abilitare lo strumento SEFAUtil nella topologia|Utilizzare il cmdlet New-CsTrustedApplicationPool per creare un nuovo pool di applicazioni attendibili. Utilizzare il cmdlet New-CsTrustedApplication per specificare lo strumento SEFAUtil come applicazione attendibile. Eseguire il cmdlet Enable-CsTopology per abilitare la topologia. Se non è già disponibile, scaricare la versione Skype for Business Server dello strumento SEFAUtil da questo percorso e installarla nel pool di applicazioni attendibili creato nel passaggio 1. Verificare che SEFAUtil sia in esecuzione correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione. |RTCUniversalServerAdmins  <br/> |[Distribuire lo strumento SEFAUtil in Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype for Business Server strumenti del Resource Kit 2015](../../management-tools/resource-kit-tools.md). Ad Skype for Business Server è necessario utilizzare la versione corrente dello strumento, ma la documentazione di Lync Server 2013 è ancora valida.  <br/> |
|Configurare gli intervalli di numeri di prelievo chiamata nella tabella orbit del parcheggio di chiamata  <br/> |Utilizzare il cmdlet **New-CSCallParkOrbit** per creare intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata e assegnare agli intervalli di prelievo delle chiamate il tipo **GroupPickup.**  <br/> Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri sono in genere configurati come un blocco di interni virtuali. L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di intervallo nella tabella orbit del parcheggio di chiamata non è supportata.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creare o modificare un intervallo di numeri di prelievo chiamata di gruppo in Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Assegnare un numero di prelievo chiamata agli utenti e abilitare la risposta alle chiamate di gruppo per gli utenti  <br/> |Utilizzare il parametro /enablegrouppickup nello strumento SEFAUtil resource kit per abilitare la risposta alle chiamate di gruppo e assegnare un numero di prelievo chiamata per gli utenti.  <br/> |-  <br/> |[Abilitare la risposta alle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificare agli utenti il numero di prelievo della chiamata assegnato e qualsiasi altro numero di interesse  <br/> |Dopo aver abilitato la risposta alle chiamate di gruppo per gli utenti, usa la posta elettronica o un altro meccanismo per notificare agli utenti il numero del gruppo di prelievo delle chiamate. Informare gli utenti del numero del gruppo di prelievo chiamata per qualsiasi gruppo che potrebbe voler monitorare. Poiché gli utenti possono recuperare le chiamate per altri utenti anche se non fanno parte dello stesso gruppo, è possibile che gli utenti necessitino del numero del gruppo di prelievo delle chiamate per più gruppi.  <br/> |-  <br/> ||
|Verificare la distribuzione di Prelievo chiamata di gruppo  <br/> | Testare il posizionamento e il recupero delle chiamate per verificare che la configurazione funzioni come previsto. Verificare quanto segue: <br/>  Chiama un utente abilitato per la risposta alle chiamate di gruppo e che un altro utente recupererà la chiamata. L'altro utente può essere nello stesso gruppo, in un gruppo diverso o non avere la risposta alle chiamate di gruppo abilitata. <br/>  Chiama un utente abilitato per la risposta alle chiamate di gruppo e non risponde alla chiamata. <br/> |-  <br/> ||
