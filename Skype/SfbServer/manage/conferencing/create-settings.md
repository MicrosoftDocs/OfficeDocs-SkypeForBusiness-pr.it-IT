---
title: Creare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Riepilogo: informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 862ffc56fd14c446a747a490daa0655e410e01d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119515"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Creare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile creare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Creare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Configurazione riunione.**
    
4. Nella pagina **Configurazione riunione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
    - Per creare un criterio a livello di sito, fare clic su **Configurazione sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.
    
    - Per creare un criterio a livello di pool, fare clic su **Configurazione pool**. Nel campo di ricerca **Seleziona un servizio** digitare il nome del pool per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic su un pool desiderato nell'elenco di servizi e quindi su **OK**.
    
5. Per instradare i partecipanti che accedono dalla rete PSTN (Public Switched Telephone Network ) attraverso la sala di attesa, deselezionare la casella di controllo **I chiamanti PSTN ignorano la sala di attesa**. Per impostazione predefinita, i partecipanti che accedono dalla rete PSTN passano direttamente alla riunione.
    
6. Per configurare l'utente che svolge la funzione di relatore nella riunione, in **Designa come relatore** effettuare una delle operazioni seguenti:
    
   - Per non consentire a persone diverse dall'organizzatore di svolgere la funzione di relatore, fare clic su **Nessuno**.
    
   - Per consentire solo ai partecipanti membri dell'organizzazione di svolgere la funzione di relatore, fare clic su **Società**. Questa è l'impostazione predefinita.
    
   - Per consentire a qualsiasi partecipante di fungere da relatore, fare clic su **Tutti**.
    
7. Per fare in modo che l'organizzatore selezioni il tipo di conferenza quando pianifica una riunione, deselezionare la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita**. Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.
    
8. Per impedire che gli utenti anonimi (non autenticati) vengano ammessi automaticamente, deselezionare la casella di controllo **Consenti utenti anonimi per impostazione predefinita**. Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.
    
9. Per personalizzare l'invito alla riunione che viene inviato ai partecipanti, eseguire le operazioni seguenti. Si noti che la dimensione massima degli URL e del testo del piè di pagina personalizzato è di 1 KB. Se non si specifica un valore per le personalizzazioni, queste non verranno incluse nella riunione, ad eccezione di **URL Guida**. Se non si include un URL della Guida personalizzato, nell'invito verrà visualizzato l'URL della Guida predefinito per Skype for Business. 
    
   - Per personalizzare il logo che viene visualizzato nell'invito alla riunione, immettere il percorso del logo in **URL logo**. Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 per 30 pixel. 
    
   - Per personalizzare il testo della Guida che viene visualizzato nell'invito alla riunione, immettere il percorso del testo della Guida in **URL Guida**.
    
   - Per personalizzare il testo legale che viene visualizzato nell'invito alla riunione, immettere il percorso del testo legale in **URL testo legale**.
    
   - Per personalizzare il testo del piè di pagina che viene visualizzato nell'invito alla riunione, immettere il testo in **Testo piè di pagina personalizzato**.
    
10. Fare clic su **Commit**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Creare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell

Per creare le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **New-CsMeetingConfiguration.**
  
Il comando seguente crea un nuovo set di impostazioni di configurazione delle riunioni per il sito Redmond:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, le nuove impostazioni di configurazione di riunione utilizzeranno i valori predefiniti per le relative proprietà.
  
Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di riunione che per impostazione predefinita ammettono chiunque come relatore di una riunione, utilizzare un comando simile al seguente:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

È possibile impostare più valori di proprietà includendo più parametri. Ad esempio, il comando seguente consente di ammettere tutti gli utenti a una riunione come relatori e di forzare anche gli utenti PSTN ad attendere nella sala di attesa fino a quando non vengono formalmente ammessi alla riunione:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Per ulteriori informazioni, incluso un elenco completo di parametri, vedere [New-CsMeetingConfiguration.](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)
