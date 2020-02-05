---
title: Convalidare la distribuzione di Edge in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Riepilogo: informazioni su come verificare che la distribuzione di Edge Server o pool di Edge Server funzioni in Skype for Business Server.'
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768299"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Convalidare la distribuzione di Edge in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare che la distribuzione di Edge Server o pool di Edge Server funzioni in Skype for Business Server.
  
Dopo aver distribuito il pool di Edge Server o Edge Server, è necessario sapere se funziona correttamente. Ecco alcuni aspetti che possono essere utili per confermare che l'ambiente Edge è connesso ai server interni e che gli utenti esterni possono connettersi all'ambiente di Skype for Business Server tramite il proprio Edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificare la connettività tra i server interni e gli Edge Server

Mentre la convalida della connettività viene eseguita automaticamente nel pool di Edge Server o Edge Server quando si installano i server perimetrali, è comunque possibile confermarlo con Windows PowerShell. Eseguire il cmdlet Get-CsManagementStoreReplicationStatus nel server interno che include l'Central Management Store o un computer collegato al dominio in cui sono installati i componenti principali di Skype for Business Server (OcsCore. msi).
  
Il risultato iniziale dell'uso di questo comando potrebbe dare uno stato falso, anziché vero, per la replica. Se ciò accade, eseguire il cmdlet Invoke-CsManagementStoreReplication. Assegnare un po' di tempo per completare la replica e quindi eseguire di nuovo il cmdlet Get-CsManagementStoreReplicationStatus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificare la connettività per gli utenti esterni

Abbiamo un ottimo strumento per confermare la configurazione di Edge Server e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari di Edge Server. Si tratta del [sito di connettività remota Anaylzer](https://testconnectivity.microsoft.com/). Si tratta di un sito gestito e mantenuto dal supporto Microsoft. Per usare questo strumento, passare al sito Web e seguire le istruzioni per scegliere lo scenario appropriato.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Considerazioni da tenere in considerazione durante il test della connettività degli utenti esterni

Qualsiasi test per l'accesso degli utenti esterni deve includere ogni tipo di utente interno supportato dall'organizzazione, che può includere una o tutte le opzioni seguenti:
  
- Gli utenti provenienti da almeno un dominio federato (consigliamo di testarli tutti però).
    
- Utenti anonimi.
    
- Gli utenti dell'organizzazione che si sono connessi a Skype for business in remoto, ma non usano VPN.
    
Questi test determineranno se il server perimetrale è:
  
- Ascolto sulle porte necessarie usando un client Telnet all'esterno della rete.
    
  - Ad esempio: Telnet sip.contoso.com 443
    
  - È consigliabile eseguire il test precedente nelle porte in uso nell'Edge Server o nel pool di Edge Server, a seconda della distribuzione.
    
- Esecuzione di una risoluzione DNS esterna accurata.
    
  - Dall'esterno della rete eseguire il ping di tutti i nomi di dominio completi esterni del pool di Edge Server o Edge Server. Anche se il ping non riesce, verranno visualizzati gli indirizzi IP, che possono essere paragonati agli indirizzi IP assegnati in precedenza.
    

