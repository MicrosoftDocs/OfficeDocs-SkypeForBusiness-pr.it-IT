---
title: Assegnare un criterio PIN per utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Riepilogo: certificati per la fase AV e OAuth per Skype for Business Server.'
ms.openlocfilehash: b7c353090f9eef3d2d2fbd0e6f8884121458f2f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818868"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Assegnare un criterio PIN per utente in Skype for Business Server

**Riepilogo:** I certificati di fase AV e OAuth per Skype for Business Server.
  
Il criterio PIN (Personal Identification Number) dei servizi di conferenza telefonica con accesso esterno è una delle singole impostazioni di un account utente che può essere configurato nel pannello di controllo di Skype for Business Server.
  
La distribuzione di uno o più criteri PIN per utente è facoltativa. È anche possibile distribuire solo un criterio PIN a livello globale o un criterio PIN a livello di sito. Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto. I diritti e le autorizzazioni degli utenti per l'uso dei pin per i servizi di conferenza telefonica con accesso esterno vengono automaticamente predefiniti per quelli definiti nel criterio PIN a livello globale quando non viene assegnato alcun criterio specifico a livello di sito o per utente.
  
Dopo aver creato almeno un criterio PIN per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve applicare ai pin creati e usati da un determinato utente.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Per assegnare un criterio PIN per utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Usare uno dei metodi seguenti per individuare un utente:
    
   - Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.
    
   - Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.
    
5. Opzionale Specificare altri criteri di ricerca per restringere i risultati:
    
   un. Fare clic su **Aggiungi filtro**.
    
   b. Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.
    
   c. Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.
    
   3D. A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.
    
    > [!TIP]
    > Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**. 
  
   e. Fare clic su **trova**.
    
6. Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.
    
    > [!TIP]
    > Se si desidera che gli stessi criteri PIN per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su **azioni**e quindi su **Assegna criteri**. 
  
7. In **Assegna criteri**, in **criteri PIN**, eseguire una delle operazioni seguenti:
    
    > [!NOTE]
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo **Assegna criteri** , ** \<Mantieni come\> ** è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo. Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.
  
   - Consenti a Skype for Business Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
   - Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina dei **criteri PIN** .
    
     > [!TIP]
     > Per decidere i criteri da assegnare, fare clic su **Visualizza** per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.
  
8. Al termine, fare clic su **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio PIN per utente tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri PIN per utente tramite Windows PowerShell e il cmdlet **Grant-CsPinPolicy** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Per assegnare un criterio PIN per utente a un singolo utente

- Con il comando seguente viene assegnato il criterio PIN per ogni utente RedmondPinPolicy all'utente Ken.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Per assegnare un criterio PIN per utente a più utenti

- Con il comando seguente viene assegnato il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond. Per informazioni dettagliate sul parametro LdapFilter usato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Per annullare l'assegnazione di un criterio PIN per utente

- Il comando seguente annulla l'assegnazione di qualsiasi criterio PIN per utente assegnato in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Per informazioni dettagliate, vedere [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Vedere anche

[Creare un nuovo criterio PIN in Skype for Business Server](create-a-new-pin-policy.md)
