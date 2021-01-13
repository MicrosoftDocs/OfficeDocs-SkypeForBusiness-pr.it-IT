---
title: Test di ripristino di emergenza in Skype for Business Server
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
description: Eseguire un ripristino del sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832816"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Test di ripristino di emergenza in Skype for Business Server

Eseguire un ripristino del sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato. Questo test simula un errore hardware completo per un server e contribuisce a garantire che le risorse, i piani e i dati siano disponibili per il ripristino. Provare a ruotare lo stato attivo del test ogni mese in modo che l'organizzazione verifichi ogni volta l'errore di un server o di un altro dispositivo diverso. 

Si noti che la pianificazione in base alla quale le organizzazioni eseguono i test di ripristino di emergenza variano. È molto importante che i test di ripristino di emergenza non vengano ignorati o trascurati. 

Esportare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in un file. Tra le altre cose, questo file può essere utilizzato per ripristinare queste informazioni nell'archivio di gestione centrale dopo un aggiornamento, un errore hardware o un altro problema che ha provocato la perdita di dati.

Importare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Per eseguire il backup dei dati di produzione:

- Eseguire il backup dei database RTC e LCSLog utilizzando il processo di backup standard di SQL Server per eseguire il dump del database in un dispositivo di dump di file o nastri.
- Utilizzare un'applicazione di backup di terze parti per eseguire il backup dei dati in file o su nastro.
- Utilizzare il cmdlet Export-CsUserData per creare un'esportazione XML dell'intero database RTC.
- Utilizzare il backup del file System o il backup di terze parti per eseguire il backup dei contenuti delle riunioni e dei registri di conformità.
- Utilizzare lo strumento da riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Skype for Business Server.

Il primo passaggio della procedura di failover include uno spostamento forzato degli utenti dal pool di produzione al pool di ripristino di emergenza. Si tratta di uno spostamento forzato poiché il pool di produzione non è disponibile per accettare la rilocazione dell'utente.

Il processo di spostamento degli utenti di Skype for Business Server è in effetti una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento dei record sul database SQL RTC. Questi dati possono essere ripristinati dal dispositivo di dump del backup originale dal SQL Server di produzione utilizzando il processo di ripristino di SQL Server standard o utilizzando un'utilità di backup/ripristino di terze parti.

Dopo aver ripristinato i dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza e funzionare come di consueto. Per consentire agli utenti di connettersi al pool di ripristino di emergenza, sarà necessaria una modifica di record DNS.

Il pool di produzione Skype for business verrà referenziato dai client che utilizzano la configurazione automatica e i record DNS SRV di:

- SRV: _sip. _tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Per semplificare il failover, è necessario che il record CNAME sia aggiornato per fare riferimento al nome di dominio completo di DROCSPool:

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- SIP.\<domain>
- AV.\<domain>
- webconf.\<domain>
