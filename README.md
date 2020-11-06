# xream
}
on_install() {
  check_android_version()
  ui_print "- Extracting module files"
  unzip -o "$ZIPFILE" 'system/*' -d $MODPATH >&2
}
set_permissions() {
  set_perm_recursive $MODPATH 0 0 0755 0644
}
check_android_version() {
  ui_print "- Android API version is $API"
  [[ "$API" -ge 28} ]] || abort "! Please Install in Android P and above"
}
# What does this module change?
persist.dbg.ims_volte_enable=1 
<br>persist.dbg.volte_avail_ovr=1 
<br>persist.dbg.vt_avail_ovr=1
<br>persist.dbg.wfc_avail_ovr=1
<br>persist.radio.rat_on=combine
<br>persist.radio.data_ltd_sys_ind=1
<br>persist.radio.data_con_rprt=1
<br>persist.radio.calls.on.ims=1
