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
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: La tabella seguente elenca i cmdlet di Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti ad altre informazioni.
ms.openlocfilehash: 58fed82857138bf9716db88648344e9140b29d6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194544"
---
# <a name="cloud-connector-cmdlet-reference"></a>Informazioni di riferimento sui cmdlet di Cloud Connector
 
La tabella seguente elenca i cmdlet di Skype for Business Cloud Connector Edition con una breve descrizione e collegamenti ad altre informazioni.
  
> [!NOTE]
> È necessario eseguire tutti i cmdlet nel computer host del Cloud Connector ed eseguire la sessione di PowerShell come amministratore. 
  
|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versione 1.4.2 e successive  <br/> |Esegue il backup del servizio autorità di certificazione in un file e lo salva nella cartella CA nella directory della condivisione del sito.     <br/> |
|[Convertire-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crea un file di disco rigido virtuale di base (VHDX) usando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà usato durante il connettore ofCloud di distribuzione.  <br/> |
|[Invio-CcUpdate](enter-ccupdate.md) <br/> |Prepara il server host Cloud Connector per il processo di aggiornamento inserendolo in modalità di manutenzione. L'apparecchio viene "svuotato"; tutte le chiamate esistenti verranno completate, ma le nuove chiamate vengono rifiutate.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Chiude la modalità di manutenzione degli aggiornamenti nel server host Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Esporta una configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Esporta un file di configurazione di esempio per il Cloud Connector (INI) nella directory appliance di un appliance di connessione cloud. È possibile modificare e rinominare il file da usare per la distribuzione.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Esporta il certificato della CA radice in un file locale nel server host Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera la directory di lavoro nel server host Cloud Connector. Tutti i file di distribuzione sono archiviati in questa directory.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Mostra la directory corrente in cui sono archiviati i registri per un appliance del connettore Cloud.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versione 2,1 e successive  <br/> |Fornisce informazioni di diagnostica per l'accessorio Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Restituisce le credenziali della distribuzione del connettore Cloud corrente.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Restituisce il percorso del file del certificato esterno per la distribuzione di Cloud Connector. L'utente prepara questo certificato.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione del disco rigido virtuale di base e del connettore Cloud. Questa cartella deve essere condivisa con tutti gli altri dispositivi di un sito del connettore Cloud.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Mostra la directory corrente in cui sono archiviati i registri a livello di sito per il connettore Cloud.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versione 2,0 e successive  <br/> |Restituisce l'istanza della versione su cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versione 2,0 e successive  <br/> |Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installa l'appliance Cloud Connector, incluse le macchine virtuali AD, Central Management store, Mediation Server e Edge Server, nel server host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ottiene le informazioni di disponibilità elevate dalla configurazione del tenant online e le pubblica nell'appliance Cloud Connector nel server host. <br/> |
|[Registro-CcAppliance](register-ccappliance.md) <br/> | Registra le informazioni sugli apparecchi in un sito PSTN in una configurazione tenant online. Un appliance deve essere registrato prima che possa essere distribuito e gestito dal servizio di gestione dei connettori cloud. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versione 1.4.2 e successive  <br/> |Rimuove il file di backup del servizio autorità\<di\>certificazione "SiteRootDirectory \CA\SfB CCE root. p12" nella cartella CA nella directory della condivisione del sito per Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Solo versione 1.4.2  <br/> |Reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Solo versione 1.4.2  <br/> |Rinnova i certificati per il connettore cloud quando la scadenza è vicina o è già scaduta.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versione 1.4.2 e successive  <br/> |Reimposta i server dell'autorità di certificazione per installare un nuovo certificato di autorità di certificazione.  <br/> |
|[Ripristinare-CcCredentials](restore-cccredentials.md) <br/> Versione 2,1 e successive  <br/> |Pulisce le credenziali e chiede di immettere di nuovo tutte le credenziali usate per la distribuzione del connettore Cloud corrente.  <br/> |
|[Ricerca-CcLog](search-cclog.md) <br/> |Esegue la ricerca nei registri delle chiamate in arrivo e in uscita nella directory del log appliance di Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Imposta la directory di lavoro nel server host Cloud Connector. Tutti i file di distribuzione sono archiviati in questa directory.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Imposta le credenziali della distribuzione di Cloud Connector corrente.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Specifica il percorso in cui è archiviato il certificato per il server di mediazione o il server perimetrale  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Cloud Connector. La cartella conterrà i file di configurazione del disco rigido virtuale e del connettore Cloud di base.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Scarica i bit del connettore Cloud e il file MSI in modo sincrono.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Genera il log delle chiamate in entrata e in uscita per un accessorio per il Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Smette di generare il log delle chiamate in entrata e in uscita per un dispositivo Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Disconnette l'appliance in uso e passa a un'appliance di backup o appena distribuita.  <br/> |
|[Disinstallare-CcAppliance](uninstall-ccappliance.md) <br/> |Disinstalla l'appliance di connessione cloud in uso dal server host.  <br/> |
|[Annullamento della registrazione-CcAppliance](unregister-ccappliance.md) <br/> |Annulla la registrazione dell'appliance del connettore Cloud corrente da un sito PSTN nella configurazione del tenant online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versione 2,0 e successive  <br/> |Reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versione 2,0 e successive  <br/> |Rinnova i certificati per il connettore cloud quando la scadenza è vicina o è già scaduta.  <br/> |
   

