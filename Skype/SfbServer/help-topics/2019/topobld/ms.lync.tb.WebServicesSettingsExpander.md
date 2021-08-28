---
title: Espansione delle impostazioni dei servizi Web
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: Da Generatore di topologie è possibile modificare le impostazioni delle porte utilizzate sia per i servizi Web interni che per i servizi Web esterni. Inoltre, se si distribuisce il bilanciamento del carico DNS (Domain Name System), è possibile utilizzare Generatore di topologie per configurare il nome di dominio completo (FQDN) del pool che si risolve negli indirizzi IP fisici di tutti i server del pool.
ms.openlocfilehash: f160259a78f5d95bd7e5e7e974579ddebe738115
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596990"
---
# <a name="web-services-settings-expander"></a>Espansione delle impostazioni dei servizi Web
 
Da Generatore di topologie è possibile modificare le impostazioni delle porte utilizzate sia per i servizi Web interni che per i servizi Web esterni. Inoltre, se si distribuisce il bilanciamento del carico DNS (Domain Name System), è possibile utilizzare Generatore di topologie per configurare il nome di dominio completo (FQDN) del pool che si risolve negli indirizzi IP fisici di tutti i server del pool.
  
### <a name="editing-web-services-settings"></a>Modifica delle impostazioni dei servizi Web

1. Selezionare il server Standard Edition Front End Server o il pool Enterprise Edition Front End corretto e fare clic su **Modifica proprietà**.
    
2. Nella finestra di dialogo **Modifica proprietà** fare clic sulla scheda **Servizi Web**.
    
    > [!CAUTION]
    > Se si dispone di più pool Front End o Front End Server, il nome di dominio completo dei servizi Web esterni deve essere univoco. Se ad esempio si definisce l'FQDN dei servizi Web esterni di un Front End Server **come pool01.contoso.com**, non è possibile utilizzare pool01.contoso.com **per** un altro pool Front End o Front End Server. Se si distribuiscono anche Director, il nome di dominio completo dei servizi Web esterni definito per qualsiasi server Director o pool di server Director deve essere univoco da qualsiasi altro server Director o pool di server Director, nonché da qualsiasi pool Front End o Front End Server. Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.
  
3. Se si modificano le proprietà di un pool Enterprise Edition, sarà possibile selezionare **Sostituisci FQDN**. Selezionare questa opzione solo se si usa il bilanciamento del carico DNS (Domain Name System). Se si usa questo tipo di bilanciamento del carico, selezionare **Sostituisci FQDN** e digitare nella casella di testo l'FQDN del pool che viene risolto negli indirizzi IP fisici di tutti i server inclusi nel pool. Se non si usa il bilanciamento del carico DNS e non si seleziona **Sostituisci FQDN**, non sarà possibile modificare l'FQDN dei servizi Web interni. L'FQDN dei servizi Web interni è l'URL utilizzato dagli utenti interni per connettersi a Skype for Business Server.
    
4. Facoltativamente, immettere nuovi valori HTTP, HTTPS o HTTP e HTTPS per **Porte di attesa** e **Porte pubblicate**. Le porte di attesa sono le porte usate da Internet Information Services (IIS) per l'attesa del traffico SIP (Session Initiation Protocol) in arrivo. Le porte pubblicate sono invece le porte configurate in un servizio o dispositivo di bilanciamento del carico oppure in un server proxy inverso e sono anch'esse usate per l'attesa del traffico SIP in arrivo. Per impostazione predefinita, la porta di attesa HTTP e la porta pubblicata HTTP sono entrambe impostate su 80. Le porte HTTPS corrispondenti sono entrambe impostate su 443. Il valore predefinito per le due porte pubblicate HTTP è 8080, mentre le porte HTTPS corrispondenti sono impostate su 4443.
    
5. Fare clic su **OK**.
    
Se si modifica l'FQDN interno o una qualsiasi assegnazione delle porte di attesa, è necessario eseguire di nuovo l'installazione locale in tutti i server del pool perché le modifiche abbiano effetto.
  

