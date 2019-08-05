---
title: Expander di impostazioni computer Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le proprietà di un server in un pool di Edge Server, eseguire le operazioni seguenti:'
ms.openlocfilehash: a6683766ddbfd11cd38d2d50b80a25c057b302bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188975"
---
# <a name="edge-machine-settings-expander"></a>Expander di impostazioni computer Edge
 
Per modificare le proprietà di un server in un pool di Edge Server, eseguire le operazioni seguenti:
  
Il **nome interno o l'FQDN** può essere modificato modificando il nome di dominio completo (FQDN). L'FQDN deve corrispondere al record host DNS (Domain Name System) (A) e al nome dell'oggetto del certificato assegnato al server per l'interfaccia di rete perimetrale interna. Il valore dell' **indirizzo IP interno** definisce l'indirizzo IP a cui viene assegnata l'interfaccia di rete definita come rete interna, rispetto alla struttura della rete perimetrale.
  
Le tre sezioni successive della finestra di dialogo definiscono gli indirizzi IP per la configurazione esterna di questo Edge Server. La possibilità di modificare gli indirizzi IP viene influenzata dall'impostazione **Abilita il nome di dominio completo e l'indirizzo IP separati per le conferenze Web e a/V** nelle impostazioni delle proprietà a livello di pool di Edge Server.
  
## <a name="sip-access"></a>Accesso SIP

Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per l'accesso SIP (Session Initiation Protocol). Questo indirizzo IP può essere un indirizzo IP pubblico o un indirizzo nell'intervallo di indirizzi IP privati.
  
> [!NOTE]
> Se l'impostazione **Abilita il nome di dominio completo e l'indirizzo IP separato per le conferenze Web e a/V** nella pagina Impostazioni pool è abilitato, solo l'indirizzo IP per l'accesso SIP sarà disponibile per la modifica.
  
## <a name="web-conferencing"></a>Web Conferencing

Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per i servizi di conferenza Web. Questo indirizzo IP può essere un indirizzo IP pubblico o un indirizzo nell'intervallo di indirizzi IP privati.
  
## <a name="audiovideo"></a>Audio/video

Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per l'audio/video (A/V). Questo indirizzo IP può essere un indirizzo IP pubblico o un indirizzo nell'intervallo di indirizzi IP privati.
  
L'impostazione per l' **indirizzo IP pubblico abilitato per NAT usato** è l'indirizzo pubblico usato dall'interfaccia esterna per l'interfaccia di rete a/V o per il server perimetrale in generale. Se l'impostazione **Abilita il nome di dominio completo e l'indirizzo IP separati per i servizi di conferenza Web e l'opzione A/V** è abilitata, questo indirizzo IP pubblico viene usato per tutte e tre le interfacce esterne.
  

