---
title: Assegnare criteri PIN per utente in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Riepilogo: assegnare criteri PIN per utente agli utenti in Skype for Business Server.'
ms.openlocfilehash: 26df2323647f295c7a1fbff41efbeae3e12b151f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675508"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Assegnare criteri PIN per utente in Skype for Business Server

**Riepilogo:** Eseguire la fase dei certificati AV e OAuth per Skype for Business Server.

Il criterio PIN (Personal Identification Number) delle conferenze telefoniche con accesso esterno è una delle singole impostazioni di un account utente che può essere configurato nel Skype for Business Server Pannello di controllo.

La distribuzione di uno o più criteri PIN per utente è facoltativa. È anche possibile distribuire solo un criterio PIN a livello globale o un criterio PIN a livello di sito. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. I diritti utente e le autorizzazioni relative all'uso dei PIN per le conferenze telefoniche con accesso esterno vengono automaticamente impostati per impostazione predefinita su quelli definiti nei criteri PIN a livello globale quando non vengono assegnati criteri specifici a livello di sito o per utente.

Dopo aver creato almeno un criterio PIN per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve imporre ai PIN creati e usati da un utente specifico.

## <a name="to-assign-a-per-user-pin-policy"></a>Per assegnare un criterio PIN per utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL Amministrazione per aprire il Skype for Business Server Pannello di controllo.

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
    > Se si desidera applicare lo stesso criterio PIN per utente a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su **Azioni** e quindi su **Assegna criteri**.

7. In **Assegna criteri**, in **Criteri PIN**, eseguire una delle operazioni seguenti:

    > [!NOTE]
    > Poiché sono disponibili più criteri che è possibile configurare tramite la finestra di dialogo **Assegna criteri** , **\<Keep as is\>** è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

   - Consenti Skype for Business Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.

   - Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina **Criteri PIN** .

     > [!TIP]
     > Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su **Visualizza** per visualizzare i diritti utente e le autorizzazioni definite nei criteri.

8. Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio PIN Per-User tramite cmdlet di Windows PowerShell

È possibile assegnare criteri PIN per utente usando Windows PowerShell e il cmdlet **Grant-CsPinPolicy**. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remote per connettersi a Skype for Business Server, vedere [Amministrazione remota di PowerShell di Microsoft Lync".](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.

### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Per assegnare un criterio PIN per utente a un singolo utente

- Il comando seguente assegna il criterio PIN per utente RedmondPinPolicy all'utente Ken Myer.

  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Per assegnare un criterio PIN per utente a più utenti

- Il comando seguente assegna il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond. Per informazioni dettagliate sul parametro LdapFilter usato in questo comando, vedere [Get-CsUser](/powershell/module/skype/get-csuser).

  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Per annullare l'assegnazione di un criterio PIN per utente

- Il comando seguente annulla l'assegnazione di eventuali criteri PIN per utente assegnati in precedenza a Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.

  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Per informazioni dettagliate, vedere [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy).

## <a name="see-also"></a>Vedere anche

[Creare un nuovo criterio PIN in Skype for Business Server](create-a-new-pin-policy.md)
