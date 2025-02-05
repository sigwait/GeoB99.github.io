+++
title = "ntoskrnl tree"
slug = "tree"
+++

## Windows Server 2003 kernel source tree

What you're seeing here is the NT kernel source tree layout of Windows Server 2003 (Service Pack 2). The source layout of Windows Server 2003 kernel is structured in a directory called **ntos** whereas **base** serves as the base operating system directory of Windows as a whole. You may wonder though, how did I obtain the said source layout of the NT kernel?

Debug checked system files contain debug information details in the binary files, alongside with source tree path strings. These strings are embedded within the checked files which are used by `RtlAssert` function. These strings can be obtained with [Strings (Sysinternals)](https://docs.microsoft.com/en-us/sysinternals/downloads/strings). Mark Russinovich also published the kernel layout tree of Windows XP Beta 2, [here](https://web.archive.org/web/20061105012217/http://www.sysinternals.com/Information/WindowsXpSourceTree.html). Although at the core the layout is basically the same between Windows Server 2003 and Windows XP Beta 2, there are some slight differences with some additional files being added.

{{<raw-html>}}
<ul class = "tree">
   <li>d:
      <ul>
         <li>base
            <ul>
               <li>ntos
                  <ul>
                     <!-- Arb -->
                     <li>arb (PnP Resource Arbiter)
                        <ul>
                           <li>arbiter.c</li>
                        </ul>
                     </li>

                     <!-- Cache -->
                     <li>cache (Cache Manager -- Cc)
                        <ul>
                           <li>cachesub.c</li>
                           <li>ccperf.c</li>
                           <li>copysup.c</li>
                           <li>fssup.c</li>
                           <li>lazyrite.c</li>
                           <li>mdlsup.c</li>
                           <li>pinsup.c</li>
                           <li>prefboot.c</li>
                           <li>prefetch.c</li>
                           <li>prefparm.c</li>
                           <li>vacbsup.c</li>
                        </ul>
                     </li>

                     <!-- Config -->
                     <li>config (Configuration Registry Manager)
                        <ul>
                           <li>i386
                              <ul>
                                 <li>geninst.c</li>
                                 <li>parseini.c</li>
                                 <li>rules.c</li>
                              </ul>
                           </li>

                           <li>cmalloc.c</li>
                           <li>cmapi.c</li>
                           <li>cmapi2.c</li>
                           <li>cmboot.c</li>
                           <li>cmchek.c</li>
                           <li>cmchek2.c</li>
                           <li>cmclose.c</li>
                           <li>cmconfig.c</li>
                           <li>cmcontrl.c</li>
                           <li>cmdelay.c</li>
                           <li>cmdelete.c</li>
                           <li>cmdown.c</li>
                           <li>cmgquota.c</li>
                           <li>cmhook.c</li>
                           <li>cmhvlist.c</li>
                           <li>cmindex.c</li>
                           <li>cminit.c</li>
                           <li>cmmapvw.c</li>
                           <li>cmnotify.c</li>
                           <li>cmparse.c</li>
                           <li>cmparse2.c</li>
                           <li>cmsavres.c</li>
                           <li>cmse.c</li>
                           <li>cmsecache.c</li>
                           <li>cmsubs.c</li>
                           <li>cmsubs2.c</li>
                           <li>cmsubs3.c</li>
                           <li>cmsysini.c</li>
                           <li>cmsysini.c</li>
                           <li>cmtrecpy.c</li>
                           <li>cmtredel.c</li>
                           <li>cmtree.c</li>
                           <li>cmvalue.c</li>
                           <li>cmworker.c</li>
                           <li>cmwrapr.c</li>
                           <li>cmwrapr2.c</li>
                           <li>hivebin.c</li>
                           <li>hivecell.c</li>
                           <li>hivechek.c</li>
                           <li>hivefree.c</li>
                           <li>hivehint.c</li>
                           <li>hiveinit.c</li>
                           <li>hiveload.c</li>
                           <li>hivemap.c</li>
                           <li>hivesync.c</li>
                           <li>hwprofil.c</li>
                           <li>ntapi.c</li>
                        </ul>
                     </li>

                     <!-- Dbgk -->
                     <li>dbgk (User-Mode Debugging Support)
                        <ul>
                           <li>dbgkobj.c</li>
                           <li>dbgkport.c</li>
                           <li>dbgkproc.c</li>
                        </ul>
                     </li>

                     <!-- Ex -->
                     <li>ex (Kernel Executive)
                        <ul>
                           <li>callback.c</li>
                           <li>exatom.c</li>
                           <li>exhotp.c</li>
                           <li>exinit.c</li>
                           <li>handle.c</li>
                           <li>harderr.c</li>
                           <li>hdlsterm.c</li>
                           <li>keyedevent.c</li>
                           <li>pool.c</li>
                           <li>probe.c</li>
                           <li>profile.c</li>
                           <li>pushlock.c</li>
                           <li>resource.c</li>
                           <li>rundown.c</li>
                           <li>sysinfo.c</li>
                           <li>systime.c</li>
                           <li>uuid.c</li>
                           <li>win32.c</li>
                           <li>worker.c</li>
                           <li>xipdisp.c</li>
                        </ul>
                     </li>

                     <!-- Fsrtl -->
                     <li>fsrtl (File System Run-Time library)
                        <ul>
                           <li>dbcsname.c</li>
                           <li>fastio.c</li>
                           <li>faulttol.c</li>
                           <li>filelock.c</li>
                           <li>filtrctx.c</li>
                           <li>fsfilter.c</li>
                           <li>fsrtlpc.c</li>
                           <li>largemcb.c</li>
                           <li>name.c</li>
                           <li>notify.c</li>
                           <li>oplock.c</li>
                           <li>pnp.c</li>
                           <li>tunnel.c</li>
                           <li>unc.c</li>
                           <li>drivesup.c</li>
                           <li>ex.c</li>
                           <li>halfnc.c</li>
                           <li>translate.c</li>
                        </ul>
                     </li>

                     <!-- Inc -->
                     <li>inc (Header Files)
                        <ul>
                           <li>ex.h</li>
                           <li>ke.h</li>
                           <li>kx.h</li>
                           <li>ob.h</li>
                        </ul>
                     </li>

                     <!-- Init -->
                     <li>init (Kernel system initialization)
                        <ul>
                           <li>bootvid.c</li>
                           <li>init.c</li>
                        </ul>
                     </li>

                     <!-- Io -->
                     <li>io (I/O and PnP managers)
                        <ul>
                           <li>
                              iomgr
                              <ul>
                                 <li>cancelapi.c</li>
                                 <li>complete.c</li>
                                 <li>create.c</li>
                                 <li>dev2dos.c</li>
                                 <li>dir.c</li>
                                 <li>dumpctl.c</li>
                                 <li>errorlog.c</li>
                                 <li>internal.c</li>
                                 <li>ioinit.c</li>
                                 <li>ioperf.c</li>
                                 <li>iosubs.c</li>
                                 <li>ioverifier.c</li>
                                 <li>loadunld.c</li>
                                 <li>lock.c</li>
                                 <li>misc.c</li>
                                 <li>objsup.c</li>
                                 <li>open.c</li>
                                 <li>parse.c</li>
                                 <li>qsea.c</li>
                                 <li>qsfs.c</li>
                                 <li>qsinfo.c</li>
                                 <li>qsquota.c</li>
                                 <li>query.c</li>
                                 <li>read.c</li>
                                 <li>triage.c</li>
                                 <li>write.c</li>
                              </ul>
                           </li>

                           <li>
                              pnpmgr
                              <ul>
                                 <li>assign.c</li>
                                 <li>convert.c</li>
                                 <li>devices.c</li>
                                 <li>devintrf.c</li>
                                 <li>devnode.c</li>
                                 <li>dockhwp.c</li>
                                 <li>iofileutil.c</li>
                                 <li>mapper.c</li>
                                 <li>notify.c</li>
                                 <li>pnpbusno.c</li>
                                 <li>pnpdd.c</li>
                                 <li>pnpdel.c</li>
                                 <li>pnpdma.c</li>
                                 <li>pnpenum.c</li>
                                 <li>pnpevent.c</li>
                                 <li>pnpinit.c</li>
                                 <li>pnpioapi.c</li>
                                 <li>pnpirp.c</li>
                                 <li>pnpirq.c</li>
                                 <li>pnpmap.c</li>
                                 <li>pnpmemio.c</li>
                                 <li>pnppower.c</li>
                                 <li>pnpres.c</li>
                                 <li>pnprlist.c</li>
                                 <li>pnpstart.c</li>
                                 <li>pnpsubs.c</li>
                                 <li>ppcddb.c</li>
                                 <li>ppcontrol.c</li>
                                 <li>ppdrvdb.c</li>
                                 <li>pphotswap.c</li>
                                 <li>pppagepath.c</li>
                                 <li>ppprofile.c</li>
                                 <li>remlock.c</li>
                                 <li>report.c</li>
                              </ul>
                           </li>

                           <li>i386
                              <ul>
                                 <li>pbiosc.c</li>
                              </ul>
                           </li>

                           <li>iovutil.c</li>
                           <li>netboot.c</li>
                           <li>sessnirp.c</li>
                           <li>trackirp.c</li>
                        </ul>
                     </li>

                     <!-- Kd64 -->
                     <li>kd64 (64-bit Kernel Debugger)
                        <ul>
                           <li>kdcpuapi.c</li>
                           <li>kdapi.c</li>
                        </ul>
                     </li>

                     <!-- Ke -->
                     <li>ke (Kernel)
                        <ul>
                           <li>i386
                              <ul>
                                 <li>allproc.c</li>
                                 <li>apcuser.c</li>
                                 <li>biosc.c</li>
                                 <li>callback.c</li>
                                 <li>cyrix.c</li>
                                 <li>exceptn.c</li>
                                 <li>flushtb.c</li>
                                 <li>gdtsup.c</li>
                                 <li>intobj.c</li>
                                 <li>kernlini.c</li>
                                 <li>largepag.c</li>
                                 <li>misc.c</li>
                                 <li>mtrr.c</li>
                                 <li>mtrramd.c</li>
                                 <li>pat.c</li>
                                 <li>vdm.c</li>
                              </ul>
                           </li>

                           <li>apcobj.c</li>
                           <li>apcsup.c</li>
                           <li>balmgr.c</li>
                           <li>bugcheck.c</li>
                           <li>devquobj.c</li>
                           <li>dpcobj.c</li>
                           <li>dpcsup.c</li>
                           <li>eventobj.c</li>
                           <li>gateobj.c</li>
                           <li>idsched.c</li>
                           <li>miscc.c</li>
                           <li>mutntobj.c</li>
                           <li>procobj.c</li>
                           <li>profobj.c</li>
                           <li>queueobj.c</li>
                           <li>semphobj.c</li>
                           <li>thredobj.c</li>
                           <li>thredsup.c</li>
                           <li>timerobj.c</li>
                           <li>timersup.c</li>
                           <li>wait.c</li>
                           <li>waitsup.c</li>
                           <li>yield.c</li>
                        </ul>
                     </li>

                     <!-- Lpc -->
                     <li>lpc (Local Procedure Call)
                        <ul>
                           <li>lpcclose.c</li>
                           <li>lpccompl.c</li>
                           <li>lpcconn.c</li>
                           <li>lpccreat.c</li>
                           <li>lpclistn.c</li>
                           <li>lpcpriv.c</li>
                           <li>lpcquery.c</li>
                           <li>lpcqueue.c</li>
                           <li>lpcrecv.c</li>
                           <li>lpcreply.c</li>
                           <li>lpcsend.c</li>
                        </ul>
                     </li>

                     <!-- Mm -->
                     <li>mm (Memory Manager)
                        <ul>
                           <li>i386
                              <ul>
                                 <li>init386.c</li>
                                 <li>procx86.c</li>
                              </ul>
                           </li>

                           <li>acceschk.c</li>
                           <li>addrsup.c</li>
                           <li>allocpag.c</li>
                           <li>allocvm.c</li>
                           <li>crashdmp.c</li>
                           <li>creasect.c</li>
                           <li>debugsup.c</li>
                           <li>deleteva.c</li>
                           <li>dmpaddr.c</li>
                           <li>dynmem.c</li>
                           <li>extsect.c</li>
                           <li>flushsec.c</li>
                           <li>forksup.c</li>
                           <li>freevm.c</li>
                           <li>hypermap.c</li>
                           <li>iosup.c</li>
                           <li>lockvm.c</li>
                           <li>mapcache.c</li>
                           <li>mapview.c</li>
                           <li>mirror.c</li>
                           <li>mmfault.c</li>
                           <li>mminit.c</li>
                           <li>mmpatch.c</li>
                           <li>mmquota.c</li>
                           <li>mmsup.c</li>
                           <li>modwrite.c</li>
                           <li>pagfault.c</li>
                           <li>pfndec.c</li>
                           <li>pfnlist.c</li>
                           <li>pfsup.c</li>
                           <li>physical.c</li>
                           <li>procsup.c</li>
                           <li>protect.c</li>
                           <li>querysec.c</li>
                           <li>queryvm.c</li>
                           <li>readwrt.c</li>
                           <li>sectsup.c</li>
                           <li>session.c</li>
                           <li>sessload.c</li>
                           <li>shutdown.c</li>
                           <li>specpool.c</li>
                           <li>sysload.c</li>
                           <li>sysptes.c</li>
                           <li>triage.c</li>
                           <li>umapview.c</li>
                           <li>vadtree.c</li>
                           <li>verifier.c</li>
                           <li>wrtfault.c</li>
                           <li>wrtwatch.c</li>
                           <li>wslist.c</li>
                           <li>wsmanage.c</li>
                           <li>wstree.c</li>
                           <li>zeropage.c</li>
                        </ul>
                     </li>

                     <!-- Ob -->
                     <li>ob (Object Manager)
                        <ul>
                           <li>obclose.c</li>
                           <li>obcreate.c</li>
                           <li>obdevmap.c</li>
                           <li>obdir.c</li>
                           <li>obhandle.c</li>
                           <li>obinit.c</li>
                           <li>obinsert.c</li>
                           <li>oblink.c</li>
                           <li>obquery.c</li>
                           <li>obref.c</li>
                           <li>obsdata.c</li>
                           <li>obse.c</li>
                           <li>obtype.c</li>
                           <li>obvutil.c</li>
                           <li>obwait.c</li>
                        </ul>
                     </li>
                     <!-- Perf -->
                     <li>perf (Performance Monitoring Manager)
                        <ul>
                           <li>hooks.c</li>
                           <li>logging.c</li>
                        </ul>
                     </li>
                     <!-- Po -->
                     <li>po (Power Manager)
                        <ul>
                           <li>attrib.c</li>
                           <li>hiber.c</li>
                           <li>idle.c</li>
                           <li>misc.c</li>
                           <li>notify.c</li>
                           <li>ntapi.c</li>
                           <li>paction.c</li>
                           <li>pbatt.c</li>
                           <li>pidle.c</li>
                           <li>pinfo.c</li>
                           <li>pocall.c</li>
                           <li>poinit.c</li>
                           <li>poshtdwn.c</li>
                           <li>postate.c</li>
                           <li>pwork.c</li>
                           <li>switch.c</li>
                           <li>sys.c</li>
                           <li>sysdev.c</li>
                           <li>thermal.c</li>
                           <li>throttle.c</li>
                        </ul>
                     </li>
                     <!-- Ps -->
                     <li>ps (Process Manager)
                        <ul>
                           <li>i386
                              <ul>
                                 <li>psctx386.c</li>
                                 <li>psldt.c</li>
                                 <li>psvdm.c</li>
                              </ul>
                           </li>
                           <li>create.c</li>
                           <li>pscid.c</li>
                           <li>psctx.c</li>
                           <li>psdelete.c</li>
                           <li>psenum.c</li>
                           <li>pshelper.c</li>
                           <li>psinit.c</li>
                           <li>psjob.c</li>
                           <li>psopen.c</li>
                           <li>psquery.c</li>
                           <li>psquota.c</li>
                           <li>psspnd.c</li>
                           <li>security.c</li>
                        </ul>
                     </li>
                     <!-- Raw -->
                     <li>raw (Unmounted File System Driver)
                        <ul>
                           <li>cleanup.c</li>
                           <li>close.c</li>
                           <li>create.c</li>
                           <li>fileinfo.c</li>
                           <li>fsctrl.c</li>
                           <li>rawdisp.c</li>
                           <li>readwrit.c</li>
                           <li>strucsup.c</li>
                           <li>strucsup.c</li>
                           <li>volinfo.c</li>
                        </ul>
                     </li>
                     <!-- Rtl -->
                     <li>rtl (Run-Time Kernel Library)
                        <ul>
                           <li>i386
                              <ul>
                                 <li>context.c</li>
                              </ul>
                           </li>
                           <li>acledit.c</li>
                           <li>atom.c</li>
                           <li>avltable.c</li>
                           <li>bitmap.c</li>
                           <li>bootstatus.c</li>
                           <li>checksum.c</li>
                           <li>cnvint.c</li>
                           <li>compress.c</li>
                           <li>excptdbg.c</li>
                           <li>gen8dot3.c</li>
                           <li>gentable.c</li>
                           <li>guid.c</li>
                           <li>heap.c</li>
                           <li>ldrreloc.c</li>
                           <li>ldrrsrc.c</li>
                           <li>lznt1.c</li>
                           <li>message.c</li>
                           <li>nls.c</li>
                           <li>nlsxlat.c</li>
                           <li>prefix.c</li>
                           <li>prodtype.c</li>
                           <li>random.c</li>
                           <li>range.c</li>
                           <li>regutil.c</li>
                           <li>rtlassig.c</li>
                           <li>rtldowncaseunicodechar.c</li>
                           <li>rtlvalidateunicodestring.c</li>
                           <li>sertl.c</li>
                           <li>string.c</li>
                           <li>tracedb.c</li>
                           <li>version.c</li>
                        </ul>
                     </li>
                     <!-- Se -->
                     <li>se (Security Monitoring Manager)
                        <ul>
                           <li>accessck.c</li>
                           <li>adtinit.c</li>
                           <li>adtlog.c</li>
                           <li>adtutil.c</li>
                           <li>capture.c</li>
                           <li>privileg.c</li>
                           <li>rmaudit.c</li>
                           <li>rmlogon.c</li>
                           <li>rmmain.c</li>
                           <li>rmvars.c</li>
                           <li>seassign.c</li>
                           <li>seastate.c</li>
                           <li>seaudit.c</li>
                           <li>seclient.c</li>
                           <li>seglobal.c</li>
                           <li>seinit.c</li>
                           <li>semethod.c</li>
                           <li>sepaudit.c</li>
                           <li>subject.c</li>
                           <li>token.c</li>
                           <li>tokenadj.c</li>
                           <li>tokendup.c</li>
                           <li>tokenopn.c</li>
                           <li>tokenp.h</li>
                           <li>tokenqry.c</li>
                           <li>tokenset.c</li>
                        </ul>
                     </li>
                     <!-- Vdm -->
                     <li>vdm (Virtual DOS Machine)
                        <ul>
                           <li>rdwr.c</li>
                           <li>strtexec.c</li>
                           <li>vdmentry.c</li>
                           <li>vdmfault.c</li>
                           <li>vdminit.c</li>
                           <li>vdmints.c</li>
                           <li>vdmnpx.c</li>
                           <li>vdmprint.c</li>
                           <li>vdmtib.c</li>
                        </ul>
                     </li>
                     <!-- Verifier -->
                     <li>verifier (Driver verifier)
                        <ul>
                           <li>vfddi.c</li>
                           <li>vfdeadlock.c</li>
                           <li>vfdevobj.c</li>
                           <li>vffilter.c</li>
                           <li>vfgeneric.c</li>
                           <li>vfhal.c</li>
                           <li>vfirp.c</li>
                           <li>vfirpdb.c</li>
                           <li>vfirplog.c</li>
                           <li>vfmessage.c</li>
                           <li>vfpacket.c</li>
                           <li>vfpnp.c</li>
                           <li>vfpower.c</li>
                           <li>vfwmi.c</li>
                        </ul>
                     </li>
                     <!-- Wmi -->
                     <li>wmi (Windows Management Instrumentation)
                        <ul>
                           <li>i386
                              <ul>
                                 <li>mcaevent.c</li>
                              </ul>
                           </li>
                           <li>alloc.c</li>
                           <li>api.c</li>
                           <li>callouts.c</li>
                           <li>chunk.c</li>
                           <li>consumer.c</li>
                           <li>dataprov.c</li>
                           <li>ds.c</li>
                           <li>enabdisa.c</li>
                           <li>globalog.c</li>
                           <li>mca.c</li>
                           <li>notify.c</li>
                           <li>provider.c</li>
                           <li>register.c</li>
                           <li>secure.c</li>
                           <li>smbios.c</li>
                           <li>traceapi.c</li>
                           <li>tracelog.c</li>
                           <li>tracesup.c</li>
                           <li>wmi.c</li>
                        </ul>
                     </li>
                  </ul>
               </li>
            </ul>
         </li>
      </ul>
   </li>
</ul>
{{</raw-html>}}
