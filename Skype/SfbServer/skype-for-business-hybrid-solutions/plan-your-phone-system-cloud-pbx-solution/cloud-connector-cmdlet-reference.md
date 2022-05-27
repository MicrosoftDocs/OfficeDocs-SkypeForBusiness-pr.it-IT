---
title: Informazioni di riferimento sui cmdlet di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: Nella tabella seguente sono elencati i cmdlet Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti ad altre informazioni.
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676168"
---
# <a name="cloud-connector-cmdlet-reference"></a>Informazioni di riferimento sui cmdlet di Cloud Connector

> [!Important]
> Cloud Connector Edition ritirerà il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete telefonica locale a Teams tramite [routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Nella tabella seguente sono elencati i cmdlet Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti ad altre informazioni.
  
> [!NOTE]
> È necessario eseguire tutti i cmdlet nel computer host del connettore cloud ed è necessario eseguire la sessione di PowerShell come amministratore. 
  
|Nome cmdlet**|Descrizione|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> Versione 1.4.2 e successive|Esegue il backup del servizio autorità di certificazione in un file e lo salva nella cartella CA nella directory della condivisione del sito.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|Crea un file del disco rigido virtuale di base (VHDX) usando un cliente fornito Windows Server 2012 file ISO R2. Il file VHDX verrà usato durante la distribuzione di Connettore Cloud.|
|[Enter-CcUpdate](enter-ccupdate.md)|Prepara il server host del connettore cloud per il processo di aggiornamento inserendolo in modalità di manutenzione. L'appliance è "svuotata"; Ovvero, tutte le chiamate esistenti verranno completate, ma le nuove chiamate vengono rifiutate.|
|[Exit-CcUpdate](exit-ccupdate.md)|Esce dalla modalità di manutenzione dell'aggiornamento nel server host del connettore cloud.|
|[Export-CcConfiguration](export-ccconfiguration.md)|Esporta una configurazione Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Esporta un file di configurazione di esempio di Cloud Connector (.ini) nella directory dell'appliance di un'appliance Cloud Connector. È possibile modificare e rinominare il file da usare per la distribuzione.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> Versione 1.4.2 e successive|Esporta il certificato CA radice in un file locale nel server host del connettore cloud.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Recupera la directory di lavoro nel server host del connettore cloud. Tutti i file di distribuzione vengono archiviati in questa directory.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Mostra la directory corrente in cui vengono archiviati i log per un'appliance Cloud Connector.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> Versione 2.1 e successive|Fornisce informazioni di diagnostica per l'appliance Cloud Connector.|
|[Get-CcCredential](get-cccredential.md)|Restituisce le credenziali della distribuzione corrente del connettore cloud.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Restituisce il percorso del file del certificato esterno per la distribuzione del connettore cloud. L'utente prepara questo certificato.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|Mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione del disco rigido virtuale di base e del connettore cloud. Questa cartella deve essere condivisa con tutte le altre appliance di un sito di Cloud Connector.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Mostra la directory corrente in cui sono archiviati i log a livello di sito per Cloud Connector.|
|[Get-CcVersion](get-ccversion.md) <p> Versione 2.0 e successive|Restituisce la versione nell'istanza di Cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> Versione 2.0 e successive|Importa la configurazione Skype for Business Cloud Connector Edition da un file locale al server host del connettore cloud.|
|[Install-CcAppliance](install-ccappliance.md)|Installa l'appliance Cloud Connector, incluse le macchine virtuali AD, Central Management Store, Mediation Server e Edge Server, nel server host.|
|[Publish-CcAppliance](publish-ccappliance.md)|Ottiene informazioni a disponibilità elevata dalla configurazione del tenant online e le pubblica nell'appliance Cloud Connector nel server host.|
|[Register-CcAppliance](register-ccappliance.md)|Registra le informazioni sull'appliance in un sito PSTN in una configurazione del tenant online. Un'appliance deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione del connettore cloud.|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> Versione 1.4.2 e successive|Rimuove il file di backup del servizio autorità di certificazione "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" nella cartella CA nella directory di condivisione del sito per Cloud Connector.|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> Versione 1.4.2 e successive|Rimuove i certificati del server legacy nell'archivio di gestione centrale, nel Mediation Server e nel server perimetrale dopo aver eseguito i cmdlet Renew-CcCACertificate o Renew CcServerCertificate.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> Solo versione 1.4.2|Reinstalla il server AD del servizio Autorità di certificazione per creare un nuovo certificato CA radice.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> Solo versione 1.4.2|Rinnova i certificati per Cloud Connector quando sono prossimi alla scadenza o sono già scaduti.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> Versione 1.4.2 e successive|Reimposta i server dell'autorità di certificazione per installare un nuovo certificato dell'autorità di certificazione.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> Versione 2.1 e successive|Pulisce le credenziali e richiede di immettere nuovamente tutte le credenziali usate per la distribuzione corrente di Cloud Connector.|
|[Search-CcLog](search-cclog.md)|Cerca i log delle chiamate in ingresso e in uscita nella directory di log dell'appliance Cloud Connector|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Imposta la directory di lavoro nel server host del connettore cloud. Tutti i file di distribuzione vengono archiviati in questa directory.|
|[Set-CcCredential](set-cccredential.md)|Imposta le credenziali della distribuzione corrente del connettore cloud.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|Specifica il percorso in cui è archiviato il certificato per mediation server o server perimetrale|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Cloud Connector. La cartella conterrà i file di configurazione del disco rigido virtuale di base e del connettore cloud.|
|[Start-CcDownload](start-ccdownload.md)|Scarica i bit e il file msi del connettore cloud in modo sincrono.|
|[Start-CcLogging](start-cclogging.md)|Genera il log delle chiamate in ingresso e in uscita per un'appliance Cloud Connector.|
|[Stop-CcLogging](stop-cclogging.md)|Interrompe la generazione del log delle chiamate in ingresso e in uscita per un'appliance Cloud Connector.|
|[Switch-CcVersion](switch-ccversion.md)|Disconnette l'appliance in esecuzione e passa a un'appliance appena distribuita o di backup.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|Disinstalla l'appliance Cloud Connector in esecuzione dal server host.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|Annulla la registrazione dell'appliance Cloud Connector corrente da un sito PSTN nella configurazione del tenant online.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> Versione 2.0 e successive|Reinstalla il server AD del servizio Autorità di certificazione per creare un nuovo certificato CA radice.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> Versione 2.0 e successive|Rinnova i certificati per Cloud Connector quando sono prossimi alla scadenza o sono già scaduti.|
