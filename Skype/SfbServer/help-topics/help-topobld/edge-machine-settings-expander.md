---
title: Espansione delle impostazioni del computer perimetrale
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
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Per modificare le proprietà di un server di un pool di server perimetrali, eseguire le operazioni seguenti:'
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807126"
---
# <a name="edge-machine-settings-expander"></a>Espansione delle impostazioni del computer perimetrale
 
Per modificare le proprietà di un server di un pool di server perimetrali, eseguire le operazioni seguenti:
  
Il valore del campo **Nome o FQDN interno** può essere cambiato modificando il nome di dominio completo (FQDN). L'FQDN deve corrispondere al record host (A) DNS (Domain Name System) e al nome soggetto del certificato assegnato al server per l'interfaccia di rete perimetrale interna. Il valore del campo **Indirizzo IP interno** definisce l'indirizzo IP assegnato all'interfaccia di rete definita come rete interna rispetto alla struttura della rete perimetrale.
  
Nelle tre sezioni successive della finestra di dialogo vengono definiti gli indirizzi IP per la configurazione esterna del server perimetrale. La possibilità di modificare gli indirizzi IP dipende dall'impostazione **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** nelle proprietà a livello di pool di server perimetrali.
  
## <a name="sip-access"></a>Accesso SIP

Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per l'accesso SIP (Session Initiation Protocol). Tale indirizzo IP può essere un indirizzo IP pubblico o un indirizzo dell'intervallo di indirizzi IP privati.
  
> [!NOTE]
> Se l'impostazione **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** è abilitata nella pagina delle impostazioni del pool, sarà disponibile per la modifica solo l'indirizzo IP per l'accesso SIP.
  
## <a name="web-conferencing"></a>Web Conferencing

Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per le conferenze Web. Tale indirizzo IP può essere un indirizzo IP pubblico o un indirizzo dell'intervallo di indirizzi IP privati.
  
## <a name="audiovideo"></a>Audio/Video

Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per audio/video (A/V). Tale indirizzo IP può essere un indirizzo IP pubblico o un indirizzo dell'intervallo di indirizzi IP privati.
  
L'impostazione di **Indirizzo IP pubblico abilitato NAT utilizzato** rappresenta l'indirizzo pubblico usato dall'interfaccia esterna per l'interfaccia di rete A/V o il server perimetrale in generale. Se l'impostazione **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** è abilitata, questo indirizzo IP pubblico viene usato per tutte e tre le interfacce esterne.
  

