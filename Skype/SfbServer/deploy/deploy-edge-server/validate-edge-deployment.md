---
title: Convalidare la distribuzione edge in Skype for Business Server
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
description: 'Riepilogo: informazioni su come verificare che la distribuzione del server perimetrale o del pool di server perimetrali funzioni in Skype for Business Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804356"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Convalidare la distribuzione edge in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare che la distribuzione del server perimetrale o del pool di server perimetrali funzioni in Skype for Business Server.
  
Dopo aver distribuito il server perimetrale o il pool di server perimetrali, è necessario sapere se funziona correttamente. Ecco un paio di cose che possono essere utili per verificare che l'ambiente Edge sia connesso ai server interni e che gli utenti esterni possano connettersi all'ambiente Skype for Business Server tramite edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificare la connettività tra i server interni e i server perimetrali

Anche se la convalida della connettività viene eseguita automaticamente nel server perimetrale o nel pool di server perimetrali durante l'installazione dei server perimetrali, è comunque possibile verificarlo automaticamente con Windows PowerShell. Eseguire il cmdlet Get-CsManagementStoreReplicationStatus sul server interno che dispone dell'archivio di gestione centrale o su qualsiasi computer aggiunto a un dominio in cui sono installati i componenti di base di Skype for Business Server (OcsCore.msi).
  
Il risultato iniziale dell'esecuzione di questo comando può fornire lo stato False, anziché True, per la replica. In questo caso, eseguire il cmdlet Invoke-CsManagementStoreReplication seguente. Concedere il tempo necessario per completare la replica, quindi eseguire di Get-CsManagementStoreReplicationStatus cmdlet.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificare la connettività per gli utenti esterni

Abbiamo un ottimo strumento per confermare la configurazione del server perimetrale e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari dei server perimetrali. Si tratta del [sito Remote Connectivity Anaylzer.](https://testconnectivity.microsoft.com/) Si tratta di un sito gestito e gestito dal supporto tecnico Microsoft. Per usare questo strumento, passare al sito Web e seguire le istruzioni per scegliere lo scenario giusto.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Aspetti da considerare durante il test della connettività degli utenti esterni

Qualsiasi test per l'accesso degli utenti esterni deve includere ogni tipo di utente interno supportato dall'organizzazione, che può includere uno o tutti gli elementi seguenti:
  
- Utenti di almeno un dominio federato (è consigliabile testarli tutti).
    
- Utenti anonimi.
    
- Utenti dell'organizzazione che hanno effettuato l'accesso a Skype for Business in remoto, ma non utilizzano vpn.
    
Questi test determineranno se il server perimetrale è:
  
- È in attesa sulle porte necessarie tramite un client telnet dall'esterno della rete.
    
  - Ad esempio: telnet sip.contoso.com 443
    
  - È consigliabile eseguire il test precedente sulle porte utilizzate nel server perimetrale o nel pool di server perimetrali, a seconda della distribuzione.
    
- Esegue la risoluzione DNS esterna in modo accurato.
    
  - Dall'esterno della rete, eseguire il ping di ogni FQDN esterno del server perimetrale o del pool di server perimetrali. Anche se il ping ha esito negativo, verranno visualizzati gli indirizzi IP, che è possibile confrontare con gli indirizzi IP precedentemente assegnati.
    

