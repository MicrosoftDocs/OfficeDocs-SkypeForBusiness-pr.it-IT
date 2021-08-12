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
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: Nella tabella seguente sono elencati Skype for Business Cloud Connector Edition cmdlet con una breve descrizione e collegamenti a ulteriori informazioni.
ms.openlocfilehash: a5a29003db50f79440b6bd0393bce63b8597d90df35cded4b7b6c0114b165b97
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341491"
---
# <a name="cloud-connector-cmdlet-reference"></a>Informazioni di riferimento sui cmdlet di Cloud Connector
 
> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Nella tabella seguente sono elencati Skype for Business Cloud Connector Edition cmdlet con una breve descrizione e collegamenti a ulteriori informazioni.
  
> [!NOTE]
> È necessario eseguire tutti i cmdlet nel computer host del connettore cloud ed eseguire la sessione di PowerShell come amministratore. 
  
|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versione 1.4.2 e successive  <br/> |Consente di eseguire il backup del servizio Autorità di certificazione in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un file del disco rigido virtuale di base (VHDX) utilizzando un file ISO Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà utilizzato durante la distribuzione diCloud Connector.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara il server host Cloud Connector per il processo di aggiornamento mettendolo in modalità manutenzione. L'appliance è "svuotata"; in altri, tutte le chiamate esistenti verranno completate, ma le nuove chiamate verranno rifiutate.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Esce dalla modalità di manutenzione degli aggiornamenti nel server host cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Esporta una Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition locale. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Esporta un file di configurazione di esempio del connettore cloud (.ini) nella directory dell'appliance di un dispositivo Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Esporta il certificato della CA radice in un file locale nel server host Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera la directory di lavoro nel server host Cloud Connector. Tutti i file di distribuzione vengono archiviati in questa directory.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i registri per un'appliance Cloud Connector.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versione 2.1 e successive  <br/> |Fornisce informazioni di diagnostica per l'appliance Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Restituisce le credenziali della distribuzione corrente di Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Restituisce il percorso del file di certificato esterno per la distribuzione del connettore cloud. L'utente prepara il certificato.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione del disco rigido virtuale e del connettore cloud di base. Questa cartella deve essere condivisa con tutte le altre appliance di un sito Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Mostra la directory corrente in cui sono archiviati i registri a livello di sito per Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versione 2.0 e successive  <br/> |Restituisce la versione nell'istanza di Cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versione 2.0 e successive  <br/> |Importa la Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installa l'appliance Cloud Connector, incluse le macchine virtuali AD, Archivio di gestione centrale, Mediation Server e Server perimetrale, nel server host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ottiene informazioni sulla disponibilità elevata dalla configurazione tenant online e le pubblica nell'appliance Cloud Connector nel server host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra le informazioni sull'appliance in un sito PSTN in una configurazione tenant online. Un'appliance deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione del connettore cloud. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versione 1.4.2 e successive  <br/> |Rimuove il file di backup del servizio autorità di certificazione " \<SiteRootDirectory\> \CA\SfB CCE Root.p12" nella cartella CA nella directory della condivisione del sito per Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Rimuove i certificati server legacy nell'archivio di gestione centrale, nel Mediation Server e nel server perimetrale dopo aver eseguito i cmdlet Renew-CcCACertificate o Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo versione 1.4.2  <br/> |Reinstalla il server AD Server del servizio Autorità di certificazione per creare un nuovo certificato CA radice.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo versione 1.4.2  <br/> |Rinnova i certificati per Cloud Connector quando sono prossimi alla scadenza o sono già scaduti.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Reimposta i server dell'autorità di certificazione per installare un nuovo certificato dell'autorità di certificazione.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versione 2.1 e successive  <br/> |Pulisce le credenziali e richiede di immettere di nuovo tutte le credenziali utilizzate per la distribuzione corrente di Cloud Connector.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Cerca nei registri delle chiamate in ingresso e in uscita nella directory di registro dell'appliance Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Imposta la directory di lavoro nel server host Cloud Connector. Tutti i file di distribuzione vengono archiviati in questa directory.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Imposta le credenziali della distribuzione corrente di Cloud Connector.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Specifica il percorso in cui è archiviato il certificato per mediation server o server perimetrale  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Cloud Connector. La cartella conterrà il disco rigido virtuale di base e i file di configurazione del connettore cloud.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Scarica i bit del connettore cloud e il file msi in modo sincrono.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera il registro delle chiamate in ingresso e in uscita per un'appliance Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Interrompe la generazione del registro delle chiamate in ingresso e in uscita per un'appliance Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Disconnette l'appliance in esecuzione e passa a un'appliance appena distribuita o di backup.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Disinstalla l'appliance Cloud Connector in esecuzione dal server host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Annulla la registrazione dell'appliance Cloud Connector corrente da un sito PSTN nella configurazione tenant online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versione 2.0 e successive  <br/> |Reinstalla il server AD Server del servizio Autorità di certificazione per creare un nuovo certificato CA radice.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versione 2.0 e successive  <br/> |Rinnova i certificati per Cloud Connector quando sono prossimi alla scadenza o sono già scaduti.  <br/> |
