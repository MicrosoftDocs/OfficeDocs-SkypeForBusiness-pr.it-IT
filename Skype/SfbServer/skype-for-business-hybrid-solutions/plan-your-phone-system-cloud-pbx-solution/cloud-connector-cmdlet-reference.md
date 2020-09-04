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
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Nella tabella seguente sono elencati i cmdlet di Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti a ulteriori informazioni.
  
> [!NOTE]
> È necessario eseguire tutti i cmdlet sul computer host del connettore Cloud ed eseguire la sessione di PowerShell come amministratore. 
  
|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versione 1.4.2 e versioni successive  <br/> |Esegue il backup del servizio autorità di certificazione in un file e lo salva nella cartella CA nella directory della condivisione del sito.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un file del disco rigido virtuale di base (VHDX) utilizzando un file ISO di Windows Server 2012 R2. Il file VHDX verrà utilizzato durante il connettore ofCloud di distribuzione.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara il server host del connettore Cloud per il processo di aggiornamento inserendolo in modalità di manutenzione. L'apparecchio è "svuotato"; ovvero, tutte le chiamate esistenti verranno completate, ma le nuove chiamate vengono rifiutate.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Consente di chiudere la modalità di manutenzione dell'aggiornamento nel server host del connettore Cloud.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Esporta una configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host di Skype for Business Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Esporta un file di configurazione di esempio del connettore Cloud (con estensione ini) nella directory appliance di un dispositivo di connessione cloud. È possibile modificare e rinominare il file da utilizzare per la distribuzione.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versione 1.4.2 e versioni successive  <br/> |Esporta il certificato della CA radice in un file locale nel server host del connettore Cloud.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera la directory di lavoro nel server host del connettore Cloud. Tutti i file di distribuzione sono archiviati in questa directory.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i registri per un dispositivo di connessione cloud.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versione 2,1 e versioni successive  <br/> |Vengono fornite informazioni di diagnostica per l'accessorio Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Restituisce la credenziale della distribuzione del connettore Cloud corrente.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Restituisce il percorso del file del certificato esterno per la distribuzione del connettore Cloud. L'utente prepara questo certificato.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione del disco rigido virtuale di base e del connettore Cloud. Questa cartella deve essere condivisa con tutti gli altri dispositivi di un sito di connettori cloud.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Visualizza la directory corrente in cui sono archiviati i registri a livello di sito per il connettore Cloud.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versione 2,0 e versioni successive  <br/> |Restituisce la versione sull'istanza del connettore Cloud. Get-CCVersion può essere utilizzato solo nel computer host del connettore Cloud.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versione 2,0 e versioni successive  <br/> |Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host del connettore Cloud.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installa l'appliance del connettore Cloud, incluse le macchine virtuali AD, archivio di gestione centrale, Mediation Server e server perimetrali, nel server host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ottiene informazioni sulla disponibilità elevata dalla configurazione del tenant online e le pubblica nell'appliance del connettore Cloud sul server host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra le informazioni sull'accessorio in un sito PSTN in una configurazione tenant online. Un dispositivo deve essere registrato prima che possa essere distribuito e gestito dal servizio di gestione dei connettori cloud. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versione 1.4.2 e versioni successive  <br/> |Rimuove il file di backup del servizio autorità di certificazione " \<SiteRootDirectory\> \CA\SFB CCE root. p12" nella cartella CA nella directory della condivisione del sito per il connettore Cloud.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versione 1.4.2 e versioni successive  <br/> |Rimuove i certificati server legacy nell'archivio di gestione centrale, nel Mediation Server e nel server perimetrale dopo aver eseguito i cmdlet Renew-CcCACertificate o Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo versione 1.4.2  <br/> |Reinstalla il server AD dell'autorità di certificazione per creare un nuovo certificato CA radice.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo versione 1.4.2  <br/> |Rinnova i certificati per il connettore cloud quando sono quasi scadenza o sono già scaduti.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versione 1.4.2 e versioni successive  <br/> |Reimposta i server dell'autorità di certificazione per installare un nuovo certificato dell'autorità di certificazione.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versione 2,1 e versioni successive  <br/> |Pulisce le credenziali e richiede di immettere di nuovo tutte le credenziali utilizzate per la distribuzione del connettore Cloud corrente.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Esegue la ricerca nei registri delle chiamate in entrata e in uscita nella directory del log degli appliance del connettore Cloud  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Imposta la directory di lavoro nel server host del connettore Cloud. Tutti i file di distribuzione sono archiviati in questa directory.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Imposta la credenziale della distribuzione del connettore Cloud corrente.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Specifica il percorso in cui è archiviato il certificato per il Mediation Server o il server perimetrale  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per il connettore Cloud. La cartella conterrà i file di configurazione del disco rigido virtuale di base e del connettore Cloud.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Scarica in modo sincrono i bit del connettore Cloud e il file MSI.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera il registro delle chiamate in ingresso e in uscita per un dispositivo di connessione cloud.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Interrompe la generazione del registro delle chiamate in ingresso e in uscita per un dispositivo di connessione cloud.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Disconnette l'apparecchio in esecuzione e passa a un nuovo dispositivo di backup o di distribuzione.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Disinstalla l'appliance del connettore Cloud in esecuzione dal server host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Annulla la registrazione dell'appliance del connettore Cloud corrente da un sito PSTN nella configurazione tenant online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versione 2,0 e versioni successive  <br/> |Reinstalla il server AD dell'autorità di certificazione per creare un nuovo certificato CA radice.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versione 2,0 e versioni successive  <br/> |Rinnova i certificati per il connettore cloud quando sono quasi scadenza o sono già scaduti.  <br/> |
   

