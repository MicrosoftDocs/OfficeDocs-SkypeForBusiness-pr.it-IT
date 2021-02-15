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
description: Eseguire un ripristino di sistema per un server del pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832816"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Test di ripristino di emergenza in Skype for Business Server

Eseguire un ripristino di sistema per un server del pool Skype for Business Server per testare il processo di ripristino di emergenza documentato. Questo test consente di simulare un errore hardware completo per un server e di garantire che le risorse, i piani e i dati siano disponibili per il ripristino. Provare a ruotare l'obiettivo del test ogni mese in modo che l'organizzazione testa ogni volta l'errore di un server diverso o di un'altra attrezzatura. 

Si noti che la pianificazione in base alla quale le organizzazioni eseguono i test di ripristino di emergenza varia. È molto importante che i test di ripristino di emergenza non vengono ignorati o ignorati. 

Esportare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in un file. Tra l'altro, questo file può essere utilizzato per ripristinare queste informazioni nell'archivio di gestione centrale dopo un aggiornamento, un errore hardware o un altro problema che ha comportato la perdita di dati.

Importare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Per eseguire il backup dei dati di produzione:

- Eseguire il backup dei database RTC e LCSLog utilizzando il processo di backup SQL Server standard per eseguire il dump del database in un dispositivo di dump su file o nastro.
- Utilizzare un'applicazione di backup di terze parti per eseguire il backup dei dati su file o su nastro.
- Utilizzare il cmdlet Export-CsUserData per creare un'esportazione XML dell'intero database RTC.
- Utilizzare il backup del file system o di terze parti per eseguire il backup del contenuto delle riunioni e dei log di conformità.
- Utilizzare lo Export-CsConfiguration della riga di comando per eseguire il backup delle impostazioni di Skype for Business Server.

Il primo passaggio della procedura di failover include lo spostamento forzato degli utenti dal pool di produzione al pool di ripristino di emergenza. Si tratta di uno spostamento forzato perché il pool di produzione non sarà disponibile per accettare la rilocazione dell'utente.

Il processo utente di spostamento di Skype for Business Server è in effetti una modifica a un attributo nell'oggetto account utente oltre a un aggiornamento dei record nel database RTC SQL. Questi dati possono essere ripristinati dal dispositivo di dump di backup originale dal SQL Server di produzione utilizzando il processo di ripristino SQL Server standard o un'utilità di backup/ripristino di terze parti.

Dopo il ripristino di questi dati, gli utenti possono connettersi in modo efficace al pool di ripristino di emergenza e funzionare normalmente. Per consentire agli utenti di connettersi al pool di ripristino di emergenza, sarà necessaria una modifica al record DNS.

Il pool di Skype for Business di produzione verrà referenziato dai client utilizzando la configurazione automatica e i record DNS SRV di:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Per facilitare il failover, questo record CNAME deve essere aggiornato in modo da fare riferimento all'FQDN DROCSPool:

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
