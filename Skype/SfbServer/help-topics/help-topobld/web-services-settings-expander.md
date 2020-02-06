---
title: Espansione delle impostazioni dei servizi Web
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
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: Dall'interno di generatore di topologie è possibile modificare le impostazioni della porta usate per i servizi Web interni ed esterni. Inoltre, se si sta distribuendo il bilanciamento del carico DNS (Domain Name System), è possibile usare generatore di topologie per configurare il nome di dominio completo (FQDN) del pool che viene risolto negli indirizzi IP fisici di tutti i server del pool.
ms.openlocfilehash: ab2a93bab1717bc34e0df42fb7f4a9ed5298166c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819028"
---
# <a name="web-services-settings-expander"></a>Espansione delle impostazioni dei servizi Web
 
Dall'interno di generatore di topologie è possibile modificare le impostazioni della porta usate per i servizi Web interni ed esterni. Inoltre, se si sta distribuendo il bilanciamento del carico DNS (Domain Name System), è possibile usare generatore di topologie per configurare il nome di dominio completo (FQDN) del pool che viene risolto negli indirizzi IP fisici di tutti i server del pool.
  
### <a name="editing-web-services-settings"></a>Modifica delle impostazioni dei servizi Web

1. Selezionare il server Standard Edition Front End Server o il pool Enterprise Edition Front End corretto e fare clic su **Modifica proprietà**.
    
2. Nella finestra di dialogo **Modifica proprietà** fare clic sulla scheda **Servizi Web**.
    
    > [!CAUTION]
    > Se si dispone di più di un pool Front-end o di un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come **pool01.contoso.com**, non è possibile usare **pool01.contoso.com** per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director.
  
3. Se si modificano le proprietà di un pool Enterprise Edition, sarà possibile selezionare **Sostituisci FQDN**. Selezionare questa opzione solo se si usa il bilanciamento del carico DNS (Domain Name System). Se si usa questo tipo di bilanciamento del carico, selezionare **Sostituisci FQDN** e digitare nella casella di testo l'FQDN del pool che viene risolto negli indirizzi IP fisici di tutti i server inclusi nel pool. Se non si usa il bilanciamento del carico DNS e non si seleziona **Sostituisci FQDN**, non sarà possibile modificare l'FQDN dei servizi Web interni. L'FQDN dei servizi Web interni è l'URL usato dagli utenti interni per connettersi a Skype for Business Server.
    
4. Facoltativamente, immettere nuovi valori HTTP, HTTPS o HTTP e HTTPS per **Porte di attesa** e **Porte pubblicate**. Le porte di attesa sono le porte usate da Internet Information Services (IIS) per l'attesa del traffico SIP (Session Initiation Protocol) in arrivo. Le porte pubblicate sono invece le porte configurate in un servizio o dispositivo di bilanciamento del carico oppure in un server proxy inverso e sono anch'esse usate per l'attesa del traffico SIP in arrivo. Per impostazione predefinita, la porta di attesa HTTP e la porta pubblicata HTTP sono entrambe impostate su 80. Le porte HTTPS corrispondenti sono entrambe impostate su 443. Il valore predefinito per le due porte pubblicate HTTP è 8080, mentre le porte HTTPS corrispondenti sono impostate su 4443.
    
5. Fare clic su **OK**.
    
Se si modifica l'FQDN interno o una qualsiasi assegnazione delle porte di attesa, è necessario eseguire di nuovo l'installazione locale in tutti i server del pool perché le modifiche abbiano effetto.
  

