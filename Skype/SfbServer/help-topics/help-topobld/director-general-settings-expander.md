---
title: Espansione delle impostazioni generali del Director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Per modificare le impostazioni di un Director esistente, sono disponibili le sezioni seguenti:'
ms.openlocfilehash: f928061059ac17ccebf06705f3862440f19e8e06632dcfdfbbf4e01581fa8e6d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333678"
---
# <a name="director-general-settings-expander"></a>Espansione delle impostazioni generali di Director
 
Per modificare le impostazioni di un Director esistente, sono disponibili le sezioni seguenti:
  
- Generale
    
- Servizi Web
    


## <a name="general-settings"></a>Generale

Nome di dominio completo (FQDN) del pool di server Director. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.
  
In **Associazioni** è possibile modificare o specificare quanto segue:
  
Condivisione file per il pool di server Director da utilizzare. Selezionare una condivisione file esistente già definita in Generatore di topologie oppure fare clic su **Nuovo** per creare una nuova definizione di condivisione file.
  
Monitoraggio dell'archivio SQL Server.
  
> [!IMPORTANT]
> Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio. Se è stata creata una nuova condivisione file, questa deve trovarsi nel server designato. 
  
## <a name="web-services"></a>Servizi Web

Per modificare o specificare ulteriori impostazioni per i servizi Web nel pool di server Director, modificare o specificare le impostazioni in Servizi Web interni e Servizi Web esterni.
  
Per **Servizi Web interni** è possibile specificare quanto segue:
  
> [!CAUTION]
> Se si dispone di più pool Front End o Front End Server, il nome di dominio completo dei servizi Web esterni deve essere univoco. Se ad esempio si definisce l'FQDN dei servizi Web esterni di un Front End Server **come pool01.contoso.com**, non è possibile **utilizzare** pool01.contoso.com per un altro pool Front End o Front End Server. Se si distribuiscono anche Director, il nome di dominio completo dei servizi Web esterni definito per qualsiasi server Director o pool di server Director deve essere univoco da qualsiasi altro server Director o pool di server Director, nonché da qualsiasi pool Front End o Front End Server. Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.
  
Se si seleziona Sostituisci FQDN, sarà possibile specificare un FQDN diverso per l'identità dei Servizi Web interni nel pool. Per impostazione predefinita, l'impostazione corrisponde al nome corrente definito per il pool di server Director.
  
È possibile specificare le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. Le impostazioni predefinite, ovvero la porta 80 per HTTP e la porta 443 per HTTPS, sono le impostazioni più comuni e in genere non devono essere modificate, tranne nel caso di requisiti specifici per l'organizzazione e la progettazione dell'infrastruttura.
  
Per **Servizi Web esterni** è possibile specificare quanto segue:
  
È possibile definire il nome di dominio completo dei servizi Web esterni. L'FQDN specificato qui in genere dipenderà dai requisiti della connessione esterna, ad esempio del proxy inverso.
  
È possibile specificare le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. L'impostazione predefinita della porta 8080 per HTTP e della porta 4443 per HTTPS viene definita inizialmente. È possibile modificare queste impostazioni per le porte di attesa, in base ai requisiti previsti per il proxy inverso e la rete esterna. Le porte pubblicate vengono impostate sul valore predefinito corrispondente alla porta 80 per HTTP e alla porta 443 per HTTPS. Questi valori determinano le porte di attesa utilizzate dal pool Director o dal server Director per le richieste in arrivo. Questi valori devono essere in genere modificati solo in caso di conflitto tra i requisiti relativi alle porte nel pool. L'utilizzo degli stessi valore di porta da parte delle porte pubblicate interne ed esterne è previsto e non costituisce un conflitto.
  

