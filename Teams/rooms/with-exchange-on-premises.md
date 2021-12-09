---
title: Distribuire Microsoft Teams Rooms con Exchange locale (ibrida)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locale.
ms.openlocfilehash: 15936a805e45ce17ec35822bb02980b4d47499b8
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355615"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Distribuire Microsoft Teams Rooms con Exchange locale (ibrida)

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locali e Microsoft Teams.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni servizi ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento riguarda le distribuzioni ibride Microsoft Teams Rooms con Exchange ospitate in locale. Poiché questo tipo di distribuzione offre moltissime varianti diverse, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.
  
## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Exchange locale, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)
  
Se si distribuiscono Microsoft Teams Rooms con Exchange locale, si usano gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Questo account verrà sincronizzato con Microsoft 365 o Office 365. Sarà necessario:
  
- Creare un account e sincronizzare l'account con Azure Active Directory.

- Abilitare la cassetta postale remota e impostare le proprietà.

- Assegnare una Microsoft 365 o Office 365 licenza.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>Creare un account e sincronizzare con Azure Active Directory

1. Nello strumento Utenti e computer di **Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account Microsoft Teams Rooms, fare clic su Nuovo **e** quindi su **Utente.**

2. Digitare il nome visualizzato nella **casella Nome completo** e l'alias nella casella Nome **accesso** utente. Fare clic su **Avanti**.

3. Digitare la password per l'account. Sarà necessario digitare di nuovo per la verifica. Verificare che la **casella di controllo Password non scada** mai sia l'unica opzione selezionata.

    > [!NOTE]
    > La **selezione della password non scade** mai è un requisito per Microsoft Teams Rooms. Le regole di dominio potrebbero proibire le password che non scadono. In tal caso, sarà necessario creare un'eccezione per ogni account Microsoft Teams Rooms account.
  
4. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Al termine, passare alla pagina degli utenti del interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato sincronizzato con online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Abilitare la cassetta postale remota e impostare le proprietà

1. [Aprire la Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange remoto di PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. In Exchange PowerShell creare una cassetta postale per l'account (abilitare l'account tramite cassetta postale) eseguendo il comando seguente:

   ```PowerShell
   Enable-Mailbox ConferenceRoom01@contoso.com -Room
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. In Exchange PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono le decisioni di prenotazione della sala direttamente senza l'intervento dell'uomo).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Si tratta di una Microsoft Teams sala riunioni!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale sala denominata ConferenceRoom01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Assegnare una Microsoft 365 o Office 365 licenza

1. Connessione a Azure Active Directory. Per informazioni dettagliate Azure Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

2. È necessario che l'account della risorsa abbia una licenza Microsoft 365 o Office 365 o che Exchange e Microsoft Teams non funzionino. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account delle risorse, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In questo caso, $strLicense codice SKU visualizzato, ad esempio contoso:STANDARDPACK.

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

Per la convalida, dovrebbe essere possibile usare qualsiasi client per accedere a questo account.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
