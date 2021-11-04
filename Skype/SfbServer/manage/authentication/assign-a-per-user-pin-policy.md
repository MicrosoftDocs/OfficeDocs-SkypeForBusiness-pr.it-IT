---
title: Assegnare un criterio PIN per utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Riepilogo: stage AV and OAuth certificates for Skype for Business Server.'
ms.openlocfilehash: 2ca870ff500c5a963db17f90262c2f128c847d60
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750355"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Assegnare un criterio PIN per utente in Skype for Business Server

**Riepilogo:** Stage AV and OAuth certificates for Skype for Business Server.
  
Il criterio PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno è una delle singole impostazioni di un account utente che può essere configurato nel Skype for Business Server Pannello di controllo.
  
La distribuzione di uno o più criteri PIN per utente è facoltativa. Puoi anche distribuire solo un criterio PIN a livello globale o un criterio PIN a livello di sito. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. Le autorizzazioni e i diritti utente relativi all'utilizzo dei PIN per le conferenze telefoniche con accesso esterno vengono automaticamente predefiniti rispetto a quelli definiti nel criterio PIN a livello globale quando non vengono assegnati criteri specifici a livello di sito o per utente.
  
Dopo aver creato almeno un criterio PIN per utente, utilizzare le procedure descritte in questo argomento per assegnare il criterio che specifica i vincoli che il server deve imporre ai PIN creati e utilizzati da un utente specifico.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Per assegnare un criterio PIN per utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Utilizzare uno dei metodi seguenti per individuare un utente:
    
   - Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.
    
   - Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.
    
5. (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:
    
   a. Fare clic su **Aggiungi filtro**.
    
   b. Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.
    
   c. Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).
    
   d. A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.
    
    > [!TIP]
    > Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**. 
  
   e. Fare clic su **Trova**.
    
6. Fare clic su un utente all'interno dei risultati della ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.
    
    > [!TIP]
    > Se si desidera applicare lo stesso criterio PIN per utente a più utenti, selezionare più utenti nei risultati della ricerca, fare clic su **Azioni** e quindi su **Assegna criteri.** 
  
7. In **Assegna criteri,** in **Criteri PIN** eseguire una delle operazioni seguenti:
    
    > [!NOTE]
    > Poiché è possibile configurare più criteri  utilizzando la finestra di dialogo Assegna criteri, è selezionata per impostazione predefinita per ogni **\<Keep as is\>** criterio della finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.
  
   - Consentire Skype for Business Server di scegliere automaticamente il criterio a livello globale o, se definito, il criterio a livello di sito.
    
   - Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina **Criteri PIN.**
    
     > [!TIP]
     > Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su **Visualizza** per visualizzare i diritti utente e le autorizzazioni definite nei criteri.
  
8. Al termine, fare clic su **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio PIN Per-User tramite Windows PowerShell cmdlet

È possibile assegnare criteri PIN per utente utilizzando Windows PowerShell e il cmdlet **Grant-CsPinPolicy.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere [Microsoft Lync Remote PowerShell Administration"](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Per assegnare un criterio PIN per utente a un singolo utente

- Il comando seguente assegna il criterio PIN per utente RedmondPinPolicy all'utente Ken Myer.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Per assegnare un criterio PIN per utente a più utenti

- Il comando seguente assegna il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond. Per informazioni dettagliate sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Per annullare l'assegnazione di un criterio PIN per utente

- Il comando seguente annulla l'assegnazione di qualsiasi criterio PIN per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Per informazioni dettagliate, [vedere Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Vedere anche

[Creare un nuovo criterio PIN in Skype for Business Server](create-a-new-pin-policy.md)