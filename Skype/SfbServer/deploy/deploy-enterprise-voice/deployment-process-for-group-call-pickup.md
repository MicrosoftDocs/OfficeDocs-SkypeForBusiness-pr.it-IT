---
title: Processo di distribuzione per il ritiro delle chiamate di gruppo in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Procedura di distribuzione e passaggi per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 6f46303316bceaae28802ec27fcaea67a8ccaa08
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767469"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processo di distribuzione per il ritiro delle chiamate di gruppo in Skype for business
 
Procedura di distribuzione e passaggi per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale.
  
Il pick-up delle chiamate di gruppo consente agli utenti di rispondere alle chiamate in arrivo ai loro colleghi tramite telefoni. 
  
 Quando si distribuisce VoIP aziendale, vengono installati e abilitati automaticamente i componenti che il pick-up delle chiamate di gruppo USA viene installato e abilitato nel server front-end o Standard Edition. È tuttavia necessario usare la procedura seguente per configurare il ritiro delle chiamate di gruppo prima che sia disponibile per gli utenti.
  
**Processo di distribuzione del pickup della chiamata di gruppo**

|**Fase**|**Passaggi**|**Gruppi e ruoli obbligatori**|**Documentazione di distribuzione**|
|:-----|:-----|:-----|:-----|
|Abilitare lo strumento SEFAUtil nella topologia|Usa il cmdlet New-CsTrustedApplicationPool per creare un nuovo pool di applicazioni attendibili. Usa il cmdlet New-CsTrustedApplication per specificare lo strumento SEFAUtil come applicazione attendibile. Eseguire il cmdlet Enable-CsTopology per abilitare la topologia. Se non è già disponibile, scaricare la versione di Skype for Business Server dello strumento SEFAUtil da questo percorso e installarlo nel pool di applicazioni attendibile creato nel passaggio 1. Verificare che SEFAUtil sia in corso correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione. |RTCUniversalServerAdmins  <br/> |[Distribuire lo strumento SEFAUtil in Skype for business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015](../../management-tools/resource-kit-tools.md). Per Skype for Business Server è necessario usare la versione corrente dello strumento, ma questa documentazione di Lync Server 2013 si applica ancora.  <br/> |
|Configurare intervalli di numeri di raccolta chiamate nella tabella Orbit di Call Park  <br/> |Usa il cmdlet **New-CsCallParkOrbit** per creare intervalli di numeri di prelievo delle chiamate nella tabella Orbit di Call Park e assegnare gli intervalli di prelievo delle chiamate per il tipo **GroupPickup**.  <br/> Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri sono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri DID (Direct inwarding Dialing) come numeri di intervallo nella tabella Orbit di parcheggio delle chiamate non è supportata.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creare o modificare un intervallo di numeri di raccolta di chiamate di gruppo in Skype for business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il ritiro delle chiamate di gruppo per gli utenti  <br/> |Usa il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il ritiro delle chiamate di gruppo e assegnare un numero di prelievo chiamate per gli utenti.  <br/> |-  <br/> |[Abilitare il ritiro delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Informare gli utenti del numero di prelievo delle chiamate assegnate e di qualsiasi altro numero di interesse  <br/> |Dopo aver abilitato il ritiro delle chiamate di gruppo per gli utenti, usare la posta elettronica o un altro meccanismo per informare gli utenti del numero del gruppo di pick-up delle chiamate. Informare gli utenti del numero del gruppo di prelievo delle chiamate per qualsiasi gruppo che potrebbe voler monitorare. Poiché gli utenti possono recuperare le chiamate per altri utenti, anche se non sono nello stesso gruppo, gli utenti potrebbero richiedere il numero del gruppo di raccolta chiamate per più gruppi.  <br/> |-  <br/> ||
|Verificare la distribuzione del ritiro delle chiamate di gruppo  <br/> | Testare il posizionamento e il recupero delle chiamate per verificare che la configurazione funzioni come previsto. Verificare quanto segue: <br/>  Chiama un utente abilitato per il ritiro delle chiamate di gruppo e Chiedi a un altro utente di recuperare la chiamata. L'altro utente può essere nello stesso gruppo, in un gruppo diverso o non ha abilitato il pick-up delle chiamate di gruppo. <br/>  Chiama un utente abilitato per il ritiro delle chiamate di gruppo e non rispondere alla chiamata. <br/> |-  <br/> ||
   

