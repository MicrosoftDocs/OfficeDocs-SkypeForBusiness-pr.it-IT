---
title: Convalidare la distribuzione di Edge in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni su come verificare che la distribuzione di server perimetrali o pool di server perimetrali funzioni in Skype for Business Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804356"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Convalidare la distribuzione di Edge in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare che la distribuzione di server perimetrali o pool di server perimetrali funzioni in Skype for Business Server.
  
Dopo aver distribuito un server perimetrale o un pool di server perimetrali, è necessario sapere se funziona correttamente. Di seguito sono riportate alcune operazioni che possono essere utili per confermare che l'ambiente Edge è connesso ai server interni e che gli utenti esterni possono connettersi all'ambiente Skype for Business Server tramite il proprio Edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificare la connettività tra i server interni e i server perimetrali

Mentre la convalida della connettività viene eseguita automaticamente nel server perimetrale o nel pool di server perimetrali quando vengono installati i server perimetrali, è comunque possibile confermarla con Windows PowerShell. Eseguire il cmdlet Get-CsManagementStoreReplicationStatus sul server interno con l'archivio di gestione centrale o su un computer aggiunto al dominio in cui sono installati i componenti di base di Skype for Business Server (OcsCore.msi).
  
Il risultato iniziale dell'esecuzione di questo comando può fornire uno stato false, anziché vero, per la replica. Se ciò accade, eseguire il cmdlet Invoke-CsManagementStoreReplication. Fornire un po' di tempo per completare la replica e quindi eseguire di nuovo il cmdlet Get-CsManagementStoreReplicationStatus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificare la connettività per gli utenti esterni

È presente un ottimo strumento per confermare la configurazione del server perimetrale e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari del server perimetrale. Si tratta del [sito Anaylzer di connettività remota](https://testconnectivity.microsoft.com/). Si tratta di un sito gestito e mantenuto dal supporto tecnico Microsoft. Per utilizzare questo strumento, passare al sito Web e seguire le istruzioni riportate di seguito per scegliere lo scenario appropriato.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Considerazioni da prendere in considerazione quando si verifica la connettività degli utenti esterni

Qualsiasi test per l'accesso degli utenti esterni deve includere ogni tipo di utente interno supportato dall'organizzazione, in modo da includere una o tutte le opzioni seguenti:
  
- Utenti provenienti da almeno un dominio federato (si consiglia di testarli tutti anche se).
    
- Utenti anonimi.
    
- Gli utenti dell'organizzazione che hanno eseguito l'accesso a Skype for business in remoto, ma non utilizzano la VPN.
    
Questi test determineranno se il server perimetrale è:
  
- È in attesa sulle porte necessarie tramite un client telnet dall'esterno della rete.
    
  - Ad esempio: Telnet sip.contoso.com 443
    
  - È consigliabile eseguire il test precedente nelle porte che si sta utilizzando nel server perimetrale o nel pool di server perimetrali, a seconda della distribuzione.
    
- Esegue la risoluzione DNS esterna in modo accurato.
    
  - Al di fuori della rete, eseguire il ping di ogni FQDN esterno del server perimetrale o del pool di server perimetrali. Anche se il ping ha esito negativo, verranno visualizzati gli indirizzi IP, che possono essere confrontati con gli indirizzi IP precedentemente assegnati.
    

