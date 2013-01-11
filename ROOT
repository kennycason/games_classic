;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;							;;
;;		DBUG includer for Donkey-Kong		;;
;;							;;
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;


false	=	0		; "Everything I say..."
true	=	not false	; yes?

debug	=	true		; turn on debugging code
rom	=	false		; true if generating code for ROM
runram	=	true		; turn off ROM protection code
invinc	=	true		; true if protagonist is invincible

	link	d:main		; include DK main level after this file
	include	d:macs		; need macros for DBUG
ecode	=	$1cfc		; MEMLO

	proc			; DBUG needs enclosing PROCs
	org	$6100		; (See memory map....i'm sure it'll fit!)
dbug	=	*
	list	l		; we don't want this garbage shown
	include	d:dbug

	if	[*-[[[high *]/4]*1024]] > 31
	org	[[[high *]/4]+1]*1024
	org	[[[high *]/4]+1]*1024
	endif
	include	d:dbglst	; include dbug display-list
	assert	*<codbas	; did we overflow DK?
	eproc

	org	dbug+3		; let's setup a symbol table....
	db	'tmp   '
	dw	tmp
	db	2
	db	'tmp1  '
	dw	tmp1
	db	2
	db	'tmp2  '
	dw	tmp2
	db	2
	db	'tmp3  '
	dw	tmp3
	db	2
	db	'src   '
	dw	src
	db	1
	db	'rn    '
	dw	rn
	db	1
	db	'rinc  '
	dw	rinc
	db	1
	db	'dest  '
	dw	dest
	db	2
