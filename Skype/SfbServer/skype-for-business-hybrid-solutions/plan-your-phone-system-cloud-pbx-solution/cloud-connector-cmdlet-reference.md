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
description: Nella tabella seguente sono elencati i cmdlet di Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti a ulteriori informazioni.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359052"
---
# <a name="cloud-connector-cmdlet-reference"></a>Informazioni di riferimento sui cmdlet di Cloud Connector
 
> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Nella tabella seguente sono elencati i cmdlet di Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti a ulteriori informazioni.
  
> [!NOTE]
> È necessario eseguire tutti i cmdlet nel computer host cloud Connector ed eseguire la sessione di PowerShell come amministratore. 
  
|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versione 1.4.2 e successive  <br/> |Consente di eseguire il backup del servizio Autorità di certificazione in un file e di salvarlo nella cartella dell'autorità di certificazione nella directory della condivisione del sito.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un file del disco rigido virtuale di base (VHDX) utilizzando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà utilizzato durante la distribuzione diCloud Connector.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara il server host Cloud Connector per il processo di aggiornamento attivando la modalità di manutenzione. L'applicazione è "scaricata"; In altri modo, tutte le chiamate esistenti verranno completate, ma le nuove chiamate verranno rifiutate.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Esce dalla modalità di manutenzione degli aggiornamenti sul server host cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Esporta una configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Esporta un file di configurazione di esempio del connettore cloud (con estensione ini) nella directory appliance di un'applicazione Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Esporta il certificato CA radice in un file locale nel server host Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera la directory di lavoro nel server host cloud connector. Tutti i file di distribuzione sono archiviati in questa directory.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i registri per un'applicazione Cloud Connector.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versione 2.1 e successive  <br/> |Fornisce informazioni di diagnostica per l'applicazione Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Restituisce le credenziali della distribuzione corrente di Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Restituisce il percorso del file del certificato esterno per la distribuzione di Cloud Connector. L'utente prepara il certificato.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione del disco rigido virtuale e del connettore cloud di base. Questa cartella deve essere condivisa con tutte le altre appliance di un sito Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i log a livello di sito per Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versione 2.0 e successive  <br/> |Restituisce la versione nell'istanza di Cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versione 2.0 e successive  <br/> |Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installa l'applicazione Cloud Connector, incluse le macchine virtuali AD, Archivio di gestione centrale, Mediation Server ed Edge Server, nel server host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ottiene informazioni sulla disponibilità elevata dalla configurazione tenant online e le pubblica nell'applicazione Cloud Connector nel server host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra le informazioni sull'applicazione in un sito PSTN in una configurazione tenant online. Un'applicazione deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione Cloud Connector. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versione 1.4.2 e successive  <br/> |Rimuove il file di backup del servizio autorità di certificazione " \<SiteRootDirectory\> \CA\SfB CCE Root.p12" nella cartella CA nella directory della condivisione del sito per Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Rimuove i certificati del server legacy nell'archivio di gestione centrale, nel Mediation Server e nel server perimetrale dopo aver eseguito i cmdlet Renew-CcCACertificate o Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo versione 1.4.2  <br/> |Reinstalla il server AD del servizio Autorità di certificazione per creare un nuovo certificato CA radice.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo versione 1.4.2  <br/> |Rinnova i certificati per Cloud Connector quando sono prossimi alla scadenza o sono già scaduti.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Reimposta i server dell'autorità di certificazione per installare un nuovo certificato dell'autorità di certificazione.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versione 2.1 e successive  <br/> |Pulisce le credenziali e richiede di immettere nuovamente tutte le credenziali utilizzate per la distribuzione corrente di Cloud Connector.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Cerca i registri delle chiamate in ingresso e in uscita nella directory dei registri dell'appliance cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Imposta la directory di lavoro nel server host del connettore cloud. Tutti i file di distribuzione sono archiviati in questa directory.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Imposta le credenziali della distribuzione corrente di Cloud Connector.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Specifica il percorso in cui è archiviato il certificato per il Mediation Server o il server perimetrale  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Cloud Connector. La cartella conterrà il disco rigido virtuale di base e i file di configurazione del connettore cloud.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Scarica i bit del connettore cloud e il file msi in modo sincrono.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera il registro delle chiamate in ingresso e in uscita per un'applicazione Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Interrompe la generazione del registro chiamate in ingresso e in uscita per un'applicazione Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Disconnette l'applicazione in esecuzione e passa a un'appliance appena distribuita o di backup.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Disinstalla l'applicazione Cloud Connector in esecuzione dal server host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Annulla la registrazione dell'applicazione Cloud Connector corrente da un sito PSTN nella configurazione tenant online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versione 2.0 e successive  <br/> |Reinstalla il server AD del servizio Autorità di certificazione per creare un nuovo certificato CA radice.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versione 2.0 e successive  <br/> |Rinnova i certificati per Cloud Connector quando sono prossimi alla scadenza o sono già scaduti.  <br/> |
   

