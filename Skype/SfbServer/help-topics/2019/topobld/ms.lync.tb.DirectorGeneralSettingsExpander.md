---
title: Espansione impostazioni generali Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni di un amministratore esistente, è possibile presentarle con le sezioni seguenti:'
ms.openlocfilehash: 92d0026f2bc769f32ca635435cd71866efb75d3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189005"
---
# <a name="director-general-settings-expander"></a>Espansione impostazioni generali Director
 
Per modificare le impostazioni di un amministratore esistente, è possibile presentarle con le sezioni seguenti:
  
- Impostazioni generali
    
- Servizi Web
    

## <a name="general-settings"></a>Impostazioni generali

Nome di dominio completo (FQDN) del pool di Director. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.
  
In **Associazioni** è possibile modificare o specificare quanto segue:
  
Condivisione file per il pool di Director da usare. Selezionare una condivisione file esistente già definita in Generatore di topologia oppure fare clic su **nuovo** per creare una nuova definizione di condivisione file.
  
Monitoraggio di SQL Server Store.
  
> [!IMPORTANT]
> Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio. Se è stata creata una nuova condivisione file, la condivisione file deve essere creata nel server che si vuole designare. 
  
## <a name="web-services"></a>Servizi Web

Per modificare o specificare altre impostazioni per i servizi Web nel pool di Director, è possibile modificare o specificare le impostazioni nei servizi Web interni e nei servizi Web esterni.
  
Per i **servizi Web interni** è possibile specificare quanto segue:
  
> [!CAUTION]
> Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come **pool01.contoso.com**, non è possibile usare **pool01.contoso.com** per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director.
  
Se si seleziona Sostituisci FQDN, sarà possibile specificare un FQDN diverso per l'identità dei Servizi Web interni nel pool. Per impostazione predefinita, l'impostazione è il nome del pool corrente definito per il pool di Director.
  
È possibile specificare le porte di ascolto e pubblicazione per HTTP e HTTPS necessarie per la distribuzione. L'impostazione predefinita della porta 80 per HTTP e della porta 443 per HTTPS sono le impostazioni più comuni e in genere non è necessario modificarle, a meno che non si disponga di requisiti specifici all'interno dell'organizzazione e della struttura dell'infrastruttura.
  
Per i **servizi Web esterni**, è possibile specificare quanto segue:
  
Puoi definire il nome di dominio completo dei servizi Web esterni. L'FQDN specificato qui in genere dipenderà dai requisiti della connessione esterna, ad esempio del proxy inverso.
  
È possibile specificare le porte di ascolto e pubblicazione per HTTP e HTTPS necessarie per la distribuzione. Le impostazioni predefinite della porta 8080 per HTTP e della porta 4443 per HTTPS sono definite inizialmente. Queste impostazioni vengono modificate per le porte in ascolto in base a quali sono i requisiti per il proxy inverso e per i requisiti di rete esterna. Le porte pubblicate sono impostate su default della porta 80 per HTTP e della porta 443 per HTTPS. Questi valori determinano quali porte verrà ascoltata dal pool di Director o dal server Director per le richieste in arrivo. In genere, non è necessario modificarlo, a meno che non ci sia un conflitto di requisiti di porta nel pool. Le porte pubblicate interne ed esterne che usano gli stessi valori di porta sono previste. Non si tratta di un conflitto.
  

