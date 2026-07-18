
Gemini
Percakapan baru
Telusuri percakapan
Gambar
Video
Koleksi
Notebook baru
Laravel Master
# Procurement Document Management System (PDMS)
Semua notebook
Prompt Screener Saham Stockbit
Stockbit Screener: Atur Aturan Screening
Strategi Trading Pro dengan Anchored VWAP
S C:\Users\arbil\Documents\0 project\0 boilerplate\laravel> php artisan migrate        Illuminate\Database\QueryException    S
Membuat Indikator Trading View
Konversi Gambar PNG ke SVG
Desa Awang Bangkal Barat Raih Juara Stunting
Panduan Stack Astro, Keystatic, Cloudflare
Konsep Website KKN Jamu PKK
Latihan Tes Kompetensi Seleksi Kerja
Komitmen Wisuda 5 Tahun ke Depan
Tes Berhasil, Sistem Berjalan Baik
Panduan Isi Formulir Pelamar Kerja
Menolak Tawaran Magang Berisiko
Kriteria Foto Buku Kenangan Universitas Ma Chung
kamu adalah mesin cv checker ATS.
Cek Tanggal Berakhir Langganan
Permintaan Edit Pas Foto Formal 3x4
Ubah Foto Paspor Jadi Formal
Foto Profil Profesional untuk CV/LinkedIn
Menangani Ancaman Keamanan Komputer
Panduan Arsitektur Full Stack Laravel
Struktur Laporan Portofolio Web Development
kita kembali menjadi mahasiswa ilmun komunikasi.
Prompt AI untuk Clean Code & Maintenance
CV Translation and Optimization
Salin Tautan dengan Hati-hati
Draft Konten Repaint Sepatu Twentynine
Mengenal Bloomorist: Bisnis Florikultura Digital
Mega-Prompt AI Content & SEO Master
SQL Mapping for Product Catalog
Bloomorist Brand & Style Guide
Surat Lamaran Kerja IT Developer Mitra Foto Abadi
Pengalaman Organisasi HMP Informatika
Desain Profil LinkedIn Falachul Akhadihima
Atasi Server Kena Ransomware Perusahaan
Permintaan Gambar Latar LinkedIn Profesional
Membuat Profil Glints Developer Unggul
Bantuan Menyusun Daftar Penghargaan
Ubah Latar Belakang Foto Menjadi Merah
Pendaftaran IMIP dan Peluang Karir
Longest Increasing Subsequence Algorithm
Analisis Mendalam VPVR: Peta Likuiditas Pasar
Perbarui CV untuk Lamaran Frontend Engineer
Permintaan Gambar Produk Casablanca Lily
Proyek Bloomorist: Pengembangan Situs Web Bunga
Pembuatan CV Operational Administrator
Bantuan Rancangan Proker Individu
Prestasi Kuliah: Magang, P2MW, Sertifikasi
Optimasi SEO Bloomorist.com: Rencana Riset
Senior Web Developer: Solusi Teknis Mendalam
Ulasan Proposal Riset Teman
Analisis Kode Indikator Trading Canggih
Penambahan Fitur Deteksi Pantulan
Perbedaan Kode Indikator Trading
Riset Algoritmik Supply Demand BEI
Permintaan Foto Prewedding Prabowo Ditolak
Riset Area Supply Demand Trading Indonesia
Gemini TradeMasterIDX: Sistem Aktif
AI Trading Strategy Development Dialog
Analisis Historis dan Potensi IHSG
Ekstraksi Kode Support & Resistance
Indeks Terburuk YTD dan 1 Tahun
Deep Dive: Trading Script Algorithm Analysis
Membuat Company Profile dengan Filament
Setup Laravel Hybrid: Filament & React
Gabung Indikator EMA, S/R, SMC
Evaluasi Algoritma Indikator Trading IDX
Optimasi Algoritma dan Visual Indikator
Pine Script EMA, S/R, Gaps
Kode Pine Script Disimpan dan Direferensikan
Memisahkan Kode Machine Learning
Inflasi Indonesia: 1998 vs 2026
Analisis Saham BUVA: Wait and See
Deep Dive: Lorentzian Classification
Analisis Valuasi Emiten Nikel: NCKL Unggul
Clarifying "Data Train" Concepts
Simpan Kode Indikator Smart Money Concepts
Asisten AI Algorithmic Trading Expert
Bea Meterai Stockbit: Bukan Realized Gain
Profit Factor 0.8: Jelek, Perlu Evaluasi
Analisis ZATA: Trading Plan BoW
Analisis Saham NCKL: Wait and See
simpan ini. // This work is licensed under CC BY-NC-SA 4.0 https://creativecommons.org/licenses/by-nc-sa/4.0/ // SMC Master IDX — Fixed & Optimized for Bursa Efek Indonesia // Fixes: Fakeout logic, LinReg channel formula, OB Strength, null safety PDH/PDL/PWH/PWL //@version=5 indicator("SMC IDX [Structure, MSS, Liquidity, Valuation & Channel]", overlay=true, max_lines_count=500, max_boxes_count=500, max_labels_count=500) //============================================================================= // 1. SETTINGS & UI STYLING //============================================================================= // --- SMC Structure Settings --- grp_str    = "1. Market Structure (BOS/CHoCH/MSS)" length     = input.int(5, "Pivots Lookback", minval=3, group=grp_str) show_lbl   = input.bool(true, "Show HH/LL Labels", inline="str1", group=grp_str) show_bos   = input.bool(true, "Show BOS/CHoCH/MSS", inline="str1", group=grp_str) mss_filter = input.bool(true, "MSS Filter (Body Close)", tooltip="MSS hanya valid jika candle close di luar structure.", group=grp_str) // --- Order Block Settings --- grp_ob     = "2. Order Block (Institutional Candles)" showBull   = input.int(3, 'Show Last Bullish OBs', minval=0, inline="ob1", group=grp_ob) showBear   = input.int(3, 'Show Last Bearish OBs', minval=0, inline="ob1", group=grp_ob) useBody    = input.bool(true, 'Use Candle Body for OB', inline="ob2", group=grp_ob) showObStr  = input.bool(true, 'Show OB Strength (%)', inline="ob2", group=grp_ob) // --- FVG Settings --- grp_fvg    = "3. Fair Value Gaps (Imbalance)" show_fvg   = input.bool(true, "Show FVG", inline="fvg1", group=grp_fvg) fvg_extend = input.int(5, "Extend FVG Boxes", inline="fvg1", group=grp_fvg) // --- Valuation --- grp_val    = "4. Valuation (Premium vs Discount)" show_eq    = input.bool(true, "Show Equilibrium (50%)", group=grp_val) // --- Liquidity Statistics Settings --- grp_ls       = "5. Statistical Liquidity (Probability)" ls_length    = input.int(10, 'Liquidity Lookback', minval=3, inline="ls1", group=grp_ls) ls_threshold = input.float(1.5, 'Volume Strength (RVOL)', step=0.1, inline="ls1", group=grp_ls) ls_eq_tol    = input.float(0.1, 'EQH/EQL Tolerance (ATR)', step=0.05, inline="ls2", group=grp_ls) ls_max_back  = input.int(20, 'Max Active Swings', inline="ls2", group=grp_ls) ls_conf_bars = input.int(2, "Fakeout Conf. Bars", minval=1, group=grp_ls) // --- Daily & Weekly Levels --- grp_dl      = "6. External Liquidity (Daily & Weekly)" show_daily  = input.bool(true, "Show PDH/PDL", inline="dl1", group=grp_dl) show_weekly = input.bool(true, "Show PWH/PWL", inline="dl1", group=grp_dl) // --- Linear Regression Channel Settings --- grp_lr     = "7. Linear Regression Channel (Statistics)" show_lr    = input.bool(true, "Show LinReg Channel", inline="lr1", group=grp_lr) lr_src     = input.source(close, "Source", inline="lr1", group=grp_lr) lr_len     = input.int(100, "Length", minval=10, inline="lr2", group=grp_lr) lr_dev     = input.float(2.0, "Deviation", minval=0.1, step=0.1, inline="lr2", group=grp_lr) lr_extend  = input.bool(true, "Extend Lines", inline="lr3", group=grp_lr) lr_fibo    = input.bool(false, "Show Fibonacci", inline="lr3", group=grp_lr) lr_showbrk = input.bool(true, "Show Broken Channel", group=grp_lr) // --- Colors --- grp_col = "8. Colors & Styling" col_bull     = input.color(#1976d2, "Bullish Str", inline="c_str", group=grp_col) col_bear     = input.color(#d32f2f, "Bearish Str", inline="c_str", group=grp_col) col_mss      = input.color(#7c3aed, "MSS", inline="c_str", group=grp_col) col_text     = input.color(#37474f, "Gen Text", inline="c_gen", group=grp_col) col_eq       = input.color(#7e57c2, "EQ (50%)", inline="c_gen", group=grp_col) bullCss      = input.color(color.new(#00897b, 85), 'Bull OB', inline='c_ob1', group=grp_col) bullBreakCss = input.color(color.new(#f57c00, 85), 'Bull Brk', inline='c_ob1', group=grp_col) bearCss      = input.color(color.new(#d32f2f, 85), 'Bear OB', inline='c_ob2', group=grp_col) bearBreakCss = input.color(color.new(#f57c00, 85), 'Bear Brk', inline='c_ob2', group=grp_col) fvg_bull_css = input.color(color.new(#4caf50, 85), "Bull FVG", inline="c_fvg", group=grp_col) fvg_bear_css = input.color(color.new(#ff5252, 85), "Bear FVG", inline="c_fvg", group=grp_col) ls_col_h     = input.color(color.new(#ef5350, 40), "Liq High", inline="c_ls1", group=grp_col) ls_col_l     = input.color(color.new(#26a69a, 40), "Liq Low", inline="c_ls1", group=grp_col) ls_col_eq    = input.color(color.new(#f9a825, 0), "EQH/EQL", inline="c_ls2", group=grp_col) ls_col_taken = input.color(color.new(#546e7a, 40), "Liq Taken", inline="c_ls2", group=grp_col) col_pdh      = input.color(#424242, "PDH/PDL", inline="c_ext", group=grp_col) col_pwh      = input.color(#000000, "PWH/PWL", inline="c_ext", group=grp_col) lr_upcol     = input.color(color.new(#1976d2, 30), "LR Up", inline="c_lr", group=grp_col) lr_dncol     = input.color(color.new(#d32f2f, 30), "LR Down", inline="c_lr", group=grp_col) lr_brkcol    = input.color(color.new(#546e7a, 40), "LR Broken", inline="c_lr", group=grp_col) var line[] ob_lines_array  = array.new_line() var box[]  ob_boxes_array  = array.new_box() var box[]  fvg_boxes_array = array.new_box() //============================================================================= // 2. HELPER FUNCTIONS & TYPES //============================================================================= type ob     float top       = na     float btm       = na     int   loc       = na   // timestamp (xloc.bar_time)     bool  breaker   = false     int   break_loc = na   // timestamp saat breaker terbentuk     float strength  = na type swing     float y       = na     int   x       = na     bool  crossed = false type liq_point     float price     float vol_strength     float raw_vol     bool  is_broken     int   break_idx     line  ln     label lbl     bool  is_eq     label lbl_sweep     bool  is_swept calc_ob_strength(float top, float btm, float vol, float avg_vol, float atr14) =>     float candle_size = math.max(top - btm, syminfo.mintick)     float size_factor = math.min(candle_size / math.max(atr14 * 2.0, syminfo.mintick), 1.0)     float vol_factor  = avg_vol > 0 ? math.min(vol / (avg_vol * 2.5), 1.0) : 0.5     math.round((size_factor * 0.5 + vol_factor * 0.5) * 100, 1) swings(len) =>     var int   os  = 0     var swing top = swing.new(na, na)     var swing btm = swing.new(na, na)     upper = ta.highest(len)     lower = ta.lowest(len)     os   := high[len] > upper ? 0 : low[len] < lower ? 1 : os     if os == 0 and os[1] != 0         top := swing.new(high[len], bar_index[len])     if os == 1 and os[1] != 1         btm := swing.new(low[len], bar_index[len])     [top, btm] method display(ob id, css, break_css, show_str) =>     string txt_str = (show_str and not na(id.strength)) ? str.tostring(id.strength) + "%" : ""     if id.breaker         b1 = box.new(id.loc, id.top, id.break_loc, id.btm, border_color=css, bgcolor=css, xloc=xloc.bar_time)         b2 = box.new(id.break_loc, id.top, time + 1, id.btm, border_color=break_css, bgcolor=break_css, extend=extend.none, xloc=xloc.bar_time, text=txt_str, text_color=col_text, text_size=size.tiny, text_halign=text.align_right)         array.push(ob_boxes_array, b1)         array.push(ob_boxes_array, b2)     else         b1 = box.new(id.loc, id.top, time, id.btm, border_color=css, bgcolor=css, extend=extend.none, xloc=xloc.bar_time, text=txt_str, text_color=col_text, text_size=size.tiny, text_halign=text.align_right)         array.push(ob_boxes_array, b1) //============================================================================= // 3. MARKET STRUCTURE LOGIC //============================================================================= ph = ta.pivothigh(length, length) pl = ta.pivotlow(length,  length) float atr_gap = ta.atr(14) * 0.8 var int   trend      = 0 var float prev_ph    = na var float prev_pl    = na var float top_struct = na var float btm_struct = na bool   bull_break = false bool   bear_break = false string txt_break  = na color  col_break  = na if not na(prev_ph)     bool b_wick  = ta.crossover(high, prev_ph)     bool b_body  = ta.crossover(close, prev_ph)     bool b_valid = mss_filter ? b_body : b_wick     if b_valid         if trend != 1             bull_break := true             trend      := 1             bool is_strong = b_body             txt_break  := is_strong ? "MSS" : "CHoCH"             col_break  := is_strong ? col_mss : col_bull             line.new(bar_index, close, bar_index, prev_ph, color=col_break, style=line.style_solid, width=is_strong ? 2 : 1)         else             bull_break := true             txt_break  := "BOS"             col_break  := col_bull             line.new(bar_index, close, bar_index, prev_ph, color=col_break, style=line.style_solid, width=1) if not na(prev_pl)     bool b_wick  = ta.crossunder(low, prev_pl)     bool b_body  = ta.crossunder(close, prev_pl)     bool b_valid = mss_filter ? b_body : b_wick     if b_valid         if trend != -1             bear_break := true             trend      := -1             bool is_strong = b_body             txt_break  := is_strong ? "MSS" : "CHoCH"             col_break  := is_strong ? col_mss : col_bear             line.new(bar_index, close, bar_index, prev_pl, color=col_break, style=line.style_solid, width=is_strong ? 2 : 1)         else             bear_break := true             txt_break  := "BOS"             col_break  := col_bear             line.new(bar_index, close, bar_index, prev_pl, color=col_break, style=line.style_solid, width=1) if show_bos     if bull_break         label.new(bar_index, high + atr_gap, txt_break, color=color.new(color.white, 100), textcolor=col_break, style=label.style_none, size=size.tiny, yloc=yloc.price)     if bear_break         label.new(bar_index, low  - atr_gap, txt_break, color=color.new(color.white, 100), textcolor=col_break, style=label.style_none, size=size.tiny, yloc=yloc.price) if not na(ph)     prev_ph := ph     string txt = "H"     if not na(top_struct)         txt := ph > top_struct ? "HH" : "LH"     top_struct := ph     if show_lbl         label.new(bar_index[length], na, txt, color=color.new(color.white, 100), textcolor=col_text, style=label.style_none, size=size.tiny, yloc=yloc.abovebar) if not na(pl)     prev_pl := pl     string txt = "L"     if not na(btm_struct)         txt := pl < btm_struct ? "LL" : "HL"     btm_struct := pl     if show_lbl         label.new(bar_index[length], na, txt, color=color.new(color.white, 100), textcolor=col_text, style=label.style_none, size=size.tiny, yloc=yloc.belowbar) //============================================================================= // 4. PRECISION ORDER BLOCKS //============================================================================= n_idx = bar_index [top_sw, btm_sw] = swings(length) float vol_sma20 = ta.sma(volume, 20) float atr14     = ta.atr(14) // Bullish OB var bullish_ob = array.new<ob>(0) if close > top_sw.y and not top_sw.crossed     top_sw.crossed := true     float lowest_val = low[1]     int   lowest_idx = 1     int loop_limit   = math.min(n_idx - top_sw.x, 100)     for i = 1 to loop_limit         if low[i] < lowest_val             lowest_val := low[i]             lowest_idx := i     int ob_idx = lowest_idx     if close[lowest_idx] > open[lowest_idx]         if (lowest_idx + 1) < bar_index and close[lowest_idx + 1] < open[lowest_idx + 1]             ob_idx := lowest_idx + 1     float ob_top  = useBody ? math.max(open[ob_idx], close[ob_idx]) : high[ob_idx]     float ob_btm  = useBody ? math.min(open[ob_idx], close[ob_idx]) : low[ob_idx]     int   ob_time = time[ob_idx]     float ob_vol  = volume[ob_idx]     float avg_vol = nz(vol_sma20[ob_idx], vol_sma20)     float str_val = calc_ob_strength(ob_top, ob_btm, ob_vol, avg_vol, nz(atr14[ob_idx], atr14))     bullish_ob.unshift(ob.new(ob_top, ob_btm, ob_time, false, na, str_val)) if bullish_ob.size() > 0     for i = bullish_ob.size() - 1 to 0         element = bullish_ob.get(i)         if not element.breaker             if close < element.btm                 element.breaker   := true                 element.break_loc := time         else             if close > element.top                 bullish_ob.remove(i) // Bearish OB var bearish_ob = array.new<ob>(0) if close < btm_sw.y and not btm_sw.crossed     btm_sw.crossed := true     float highest_val = high[1]     int   highest_idx = 1     int loop_limit    = math.min(n_idx - btm_sw.x, 100)     for i = 1 to loop_limit         if high[i] > highest_val             highest_val := high[i]             highest_idx := i     int ob_idx = highest_idx     if close[highest_idx] < open[highest_idx]         if (highest_idx + 1) < bar_index and close[highest_idx + 1] > open[highest_idx + 1]             ob_idx := highest_idx + 1     float ob_top  = useBody ? math.max(open[ob_idx], close[ob_idx]) : high[ob_idx]     float ob_btm  = useBody ? math.min(open[ob_idx], close[ob_idx]) : low[ob_idx]     int   ob_time = time[ob_idx]     float ob_vol  = volume[ob_idx]     float avg_vol = nz(vol_sma20[ob_idx], vol_sma20)     float str_val = calc_ob_strength(ob_top, ob_btm, ob_vol, avg_vol, nz(atr14[ob_idx], atr14))     bearish_ob.unshift(ob.new(ob_top, ob_btm, ob_time, false, na, str_val)) if bearish_ob.size() > 0     for i = bearish_ob.size() - 1 to 0         element = bearish_ob.get(i)         if not element.breaker             if close > element.top                 element.breaker   := true                 element.break_loc := time         else             if close < element.btm                 bearish_ob.remove(i) //============================================================================= // 5. FAIR VALUE GAPS //============================================================================= if show_fvg     if low > high[2] and close[1] > high[2]         fvg_box = box.new(bar_index - 2, low,  bar_index + fvg_extend, high[2], border_color=na, bgcolor=fvg_bull_css)         array.push(fvg_boxes_array, fvg_box)     if high < low[2] and close[1] < low[2]         fvg_box = box.new(bar_index - 2, high, bar_index + fvg_extend, low[2],  border_color=na, bgcolor=fvg_bear_css)         array.push(fvg_boxes_array, fvg_box)     if array.size(fvg_boxes_array) > 50         old_fvg = array.remove(fvg_boxes_array, 0)         box.delete(old_fvg) //============================================================================= // 6. VALUATION: PREMIUM / DISCOUNT //============================================================================= var float valid_dh = na var float valid_dl = na var float pending_origin = na var bool  wait_for_ph = false var bool  wait_for_pl = false if bull_break     pending_origin := btm_struct     wait_for_ph := true     wait_for_pl := false if bear_break     pending_origin := top_struct     wait_for_pl := true     wait_for_ph := false if not na(ph) and wait_for_ph     valid_dh := ph     valid_dl := pending_origin     wait_for_ph  := false if not na(pl) and wait_for_pl     valid_dl := pl     valid_dh := pending_origin     wait_for_pl  := false var line  dh_line = na var label dh_lbl  = na var line  eq_line = na var label eq_lbl  = na var line  dl_line = na var label dl_lbl  = na if show_eq     line.delete(dh_line),  label.delete(dh_lbl)     line.delete(eq_line),  label.delete(eq_lbl)     line.delete(dl_line),  label.delete(dl_lbl)     if not na(valid_dh) and not na(valid_dl) and valid_dh != valid_dl         float mid_price = (valid_dh + valid_dl) / 2         int start_idx   = bar_index - length         int end_idx     = bar_index + 12         dh_line := line.new(start_idx, valid_dh, end_idx, valid_dh, color=color.new(col_eq, 60), style=line.style_solid, width=1)         dh_lbl  := label.new(end_idx, valid_dh, " Premium", color=color.new(color.white, 100), textcolor=color.new(col_text, 20), style=label.style_none, size=size.small)         eq_line := line.new(start_idx, mid_price, end_idx, mid_price, color=color.new(col_eq, 20), style=line.style_dotted, width=1)         eq_lbl  := label.new(end_idx, mid_price, " EQ 50%", color=color.new(color.white, 100), textcolor=color.new(col_eq, 0), style=label.style_none, size=size.small)         dl_line := line.new(start_idx, valid_dl, end_idx, valid_dl, color=color.new(col_eq, 60), style=line.style_solid, width=1)         dl_lbl  := label.new(end_idx, valid_dl, " Discount", color=color.new(color.white, 100), textcolor=color.new(col_text, 20), style=label.style_none, size=size.small) //============================================================================= // 7. EXTERNAL LIQUIDITY — IDX DAILY & WEEKLY //============================================================================= var float cur_d_h = na, var float cur_d_l = na var float pdh     = na, var float pdl     = na var int   cur_d_start = na if ta.change(time("D"))     pdh         := cur_d_h     pdl         := cur_d_l     cur_d_h     := high     cur_d_l     := low     cur_d_start := bar_index else     cur_d_h := math.max(nz(cur_d_h, high), high)     cur_d_l := math.min(nz(cur_d_l, low), low) var float cur_w_h = na, var float cur_w_l = na var float pwh     = na, var float pwl     = na var int   cur_w_start = na if ta.change(time("W"))     pwh         := cur_w_h     pwl         := cur_w_l     cur_w_h     := high     cur_w_l     := low     cur_w_start := bar_index else     cur_w_h := math.max(nz(cur_w_h, high), high)     cur_w_l := math.min(nz(cur_w_l, low), low) float final_pdh = not na(pdh) ? pdh : cur_d_h float final_pdl = not na(pdl) ? pdl : cur_d_l bool  is_friday_close = dayofweek == dayofweek.friday and session.islastbar_regular float final_pwh = is_friday_close ? cur_w_h : (not na(pwh) ? pwh : cur_w_h) float final_pwl = is_friday_close ? cur_w_l : (not na(pwl) ? pwl : cur_w_l) var line  l_pdh = na, var line  l_pdl = na var label lbl_pdh = na, var label lbl_pdl = na var line  l_pwh = na, var line  l_pwl = na var label lbl_pwh = na, var label lbl_pwl = na if show_daily and not na(final_pdh) and not na(final_pdl)     line.delete(l_pdh),    line.delete(l_pdl)     label.delete(lbl_pdh), label.delete(lbl_pdl)     int anchor_d   = nz(cur_d_start, bar_index - 20)     int right_ex_d = bar_index + 16     l_pdh   := line.new(anchor_d, final_pdh, right_ex_d, final_pdh, color=color.new(col_pdh, 30), style=line.style_dashed, width=1)     lbl_pdh := label.new(right_ex_d, final_pdh, " PDH", color=color.new(color.white, 100), textcolor=col_pdh, style=label.style_none, size=size.small)     l_pdl   := line.new(anchor_d, final_pdl, right_ex_d, final_pdl, color=color.new(col_pdh, 30), style=line.style_dashed, width=1)     lbl_pdl := label.new(right_ex_d, final_pdl, " PDL", color=color.new(color.white, 100), textcolor=col_pdh, style=label.style_none, size=size.small) if show_weekly and not na(final_pwh) and not na(final_pwl)     line.delete(l_pwh),    line.delete(l_pwl)     label.delete(lbl_pwh), label.delete(lbl_pwl)     int anchor_w   = nz(cur_w_start, bar_index - 100)     int right_ex_w = bar_index + 24     l_pwh   := line.new(anchor_w, final_pwh, right_ex_w, final_pwh, color=color.new(col_pwh, 20), style=line.style_dotted, width=1)     lbl_pwh := label.new(right_ex_w, final_pwh, " PWH", color=color.new(color.white, 100), textcolor=col_pwh, style=label.style_none, size=size.small)     l_pwl   := line.new(anchor_w, final_pwl, right_ex_w, final_pwl, color=color.new(col_pwh, 20), style=line.style_dotted, width=1)     lbl_pwl := label.new(right_ex_w, final_pwl, " PWL", color=color.new(color.white, 100), textcolor=col_pwh, style=label.style_none, size=size.small) //============================================================================= // 8. STATISTICAL LIQUIDITY (INTERNAL) //============================================================================= format_vol_liq(float v) =>     v >= 1000000 ? str.format("{0,number,#.#}M", v / 1000000) :      v >= 1000   ? str.format("{0,number,#.#}K", v / 1000)    :      str.tostring(v, "#") calc_rvol() =>     float avg_vol = ta.sma(volume, 50)     volume / math.max(avg_vol, 1.0) float atr_val = ta.atr(14) var liq_point[] arr_highs = array.new<liq_point>(0) var liq_point[] arr_lows  = array.new<liq_point>(0) float ls_ph_val = ta.pivothigh(ls_length, ls_length) float ls_pl_val = ta.pivotlow(ls_length,  ls_length) if not na(ls_ph_val)     float swing_rvol = calc_rvol()[ls_length]     float raw_v      = volume[ls_length]     if swing_rvol >= ls_threshold or (high[ls_length] - low[ls_length]) > atr_val         bool found_eqh = false         if array.size(arr_highs) > 0             for i = 0 to array.size(arr_highs) - 1                 liq_point prev_p = array.get(arr_highs, i)                 if math.abs(ls_ph_val - prev_p.price) < (atr_val * ls_eq_tol) and not prev_p.is_broken                     found_eqh := true                     line.set_color(prev_p.ln, ls_col_eq)                     line.set_style(prev_p.ln, line.style_dashed)                     label.set_text(prev_p.lbl, "EQH (" + format_vol_liq(prev_p.raw_vol) + ")")                     label.set_textcolor(prev_p.lbl, ls_col_eq)                     prev_p.is_eq := true                     break         color  fin_col  = found_eqh ? ls_col_eq : ls_col_h         string base_txt = found_eqh ? "EQH" : "BSL"         string full_txt = base_txt + " (" + format_vol_liq(raw_v) + ")"         line  new_ln  = line.new(bar_index[ls_length], ls_ph_val, bar_index, ls_ph_val, color=fin_col, style=found_eqh ? line.style_dashed : line.style_solid, width=1)         label new_lbl = label.new(bar_index, ls_ph_val, full_txt, color=color.new(color.white, 100), style=label.style_none, size=size.tiny, textcolor=col_text, yloc=yloc.price)         array.unshift(arr_highs, liq_point.new(ls_ph_val, swing_rvol, raw_v, false, na, new_ln, new_lbl, found_eqh, na, false))         if array.size(arr_highs) > ls_max_back             liq_point old = array.pop(arr_highs)             line.delete(old.ln),  label.delete(old.lbl)             if not na(old.lbl_sweep)                 label.delete(old.lbl_sweep) if not na(ls_pl_val)     float swing_rvol = calc_rvol()[ls_length]     float raw_v      = volume[ls_length]     if swing_rvol >= ls_threshold or (high[ls_length] - low[ls_length]) > atr_val         bool found_eql = false         if array.size(arr_lows) > 0             for i = 0 to array.size(arr_lows) - 1                 liq_point prev_p = array.get(arr_lows, i)                 if math.abs(ls_pl_val - prev_p.price) < (atr_val * ls_eq_tol) and not prev_p.is_broken                     found_eql := true                     line.set_color(prev_p.ln, ls_col_eq)                     line.set_style(prev_p.ln, line.style_dashed)                     label.set_text(prev_p.lbl, "EQL (" + format_vol_liq(prev_p.raw_vol) + ")")                     label.set_textcolor(prev_p.lbl, ls_col_eq)                     prev_p.is_eq := true                     break         color  fin_col  = found_eql ? ls_col_eq : ls_col_l         string base_txt = found_eql ? "EQL" : "SSL"         string full_txt = base_txt + " (" + format_vol_liq(raw_v) + ")"         line  new_ln  = line.new(bar_index[ls_length], ls_pl_val, bar_index, ls_pl_val, color=fin_col, style=found_eql ? line.style_dashed : line.style_solid, width=1)         label new_lbl = label.new(bar_index, ls_pl_val, full_txt, color=color.new(color.white, 100), style=label.style_none, size=size.tiny, textcolor=col_text, yloc=yloc.price)         array.unshift(arr_lows, liq_point.new(ls_pl_val, swing_rvol, raw_v, false, na, new_ln, new_lbl, found_eql, na, false))         if array.size(arr_lows) > ls_max_back             liq_point old = array.pop(arr_lows)             line.delete(old.ln),  label.delete(old.lbl)             if not na(old.lbl_sweep)                 label.delete(old.lbl_sweep) //============================================================================= // 9. INTERACTION LOGIC — FIXED LIQUIDITY SWEEP & BREAKOUT //============================================================================= float atr = atr_val // --- Highs (Buy Side Liquidity) --- if array.size(arr_highs) > 0     for i = array.size(arr_highs) - 1 to 0         liq_point p = array.get(arr_highs, i)                 if not p.is_broken             // 1. Memanjangkan garis utama hanya jika belum tersweep/breakout             line.set_x2(p.ln, bar_index)             label.set_x(p.lbl, bar_index)             // 2. Deteksi Sweep (Harga menembus dengan wick)             if high > p.price and not p.is_swept                 p.is_swept := true                 line.set_color(p.ln, ls_col_taken)                 line.set_style(p.ln, line.style_dotted) // Garis jadi putus-putus tanda sedang diuji                 label.set_textcolor(p.lbl, ls_col_taken)                                 // FIXED: Label SWEEP dicetak DIAM DI TEMPAT bar terjadinya wick                 label lbl_sw = label.new(bar_index, p.price + atr * 0.3, "SWEEP", color=color.new(color.white, 100), textcolor=ls_col_taken, style=label.style_none, size=size.tiny, yloc=yloc.price)                 p.lbl_sweep := lbl_sw             // 3. Deteksi Breakout (Harga menembus dengan Body Close)             if close > p.price                 p.is_broken := true                         // 4. Cleanup Maksimal: Jika level sudah di-break dengan body, langsung hapus semuanya!         if p.is_broken             line.delete(p.ln)             label.delete(p.lbl)             if not na(p.lbl_sweep)                 label.delete(p.lbl_sweep)             array.remove(arr_highs, i) // --- Lows (Sell Side Liquidity) --- if array.size(arr_lows) > 0     for i = array.size(arr_lows) - 1 to 0         liq_point p = array.get(arr_lows, i)                 if not p.is_broken             // 1. Memanjangkan garis utama hanya jika belum tersweep/breakout             line.set_x2(p.ln, bar_index)             label.set_x(p.lbl, bar_index)             // 2. Deteksi Sweep (Harga menembus dengan wick)             if low < p.price and not p.is_swept                 p.is_swept := true                 line.set_color(p.ln, ls_col_taken)                 line.set_style(p.ln, line.style_dotted) // Garis jadi putus-putus tanda sedang diuji                 label.set_textcolor(p.lbl, ls_col_taken)                                 // FIXED: Label SWEEP dicetak DIAM DI TEMPAT bar terjadinya wick                 label lbl_sw = label.new(bar_index, p.price - atr * 0.3, "SWEEP", color=color.new(color.white, 100), textcolor=ls_col_taken, style=label.style_none, size=size.tiny, yloc=yloc.price)                 p.lbl_sweep := lbl_sw             // 3. Deteksi Breakout (Harga menembus dengan Body Close)             if close < p.price                 p.is_broken := true                         // 4. Cleanup Maksimal: Jika level sudah di-break dengan body, langsung hapus semuanya!         if p.is_broken             line.delete(p.ln)             label.delete(p.lbl)             if not na(p.lbl_sweep)                 label.delete(p.lbl_sweep)             array.remove(arr_lows, i) //============================================================================= // 10. CLEANUP (OB boxes) //============================================================================= if array.size(ob_boxes_array) > 0     for i = array.size(ob_boxes_array) - 1 to 0         box.delete(array.get(ob_boxes_array, i))     array.clear(ob_boxes_array) if showBull > 0 and barstate.islast     for i = 0 to math.min(showBull - 1, bullish_ob.size() - 1)         bullish_ob.get(i).display(bullCss, bullBreakCss, showObStr) if showBear > 0 and barstate.islast     for i = 0 to math.min(showBear - 1, bearish_ob.size() - 1)         bearish_ob.get(i).display(bearCss, bearBreakCss, showObStr) //============================================================================= // 11. LINEAR REGRESSION CHANNEL //============================================================================= var float[] fibo_ratios = array.from(0.236, 0.382, 0.618, 0.786) var color[] lr_colors   = array.new<color>(2) if barstate.isfirst     array.set(lr_colors, 0, lr_dncol)     array.set(lr_colors, 1, lr_upcol) get_channel(src, len) =>     float y2    = ta.linreg(src, len, 0)     float y1    = ta.linreg(src, len, len - 1)     float slope = len > 1 ? (y2 - y1) / (len - 1) : 0.0     float dev   = 0.0     for i = 0 to len - 1         float expected = y2 - slope * i         dev := dev + math.pow(src[i] - expected, 2)     dev := math.sqrt(dev / len)     [y1, y2, dev, slope] if show_lr     [y1_, y2_, dev, slope] = get_channel(lr_src, lr_len)     bool below_channel = close < y2_ - dev * lr_dev     bool above_channel = close > y2_ + dev * lr_dev     int  outofchannel  = (slope > 0 and below_channel) ? 0 : (slope < 0 and above_channel) ? 2 : -1     var line[] reglines  = array.new_line(3)     var line[] fibolines = array.new_line(4)     color cur_col = array.get(lr_colors, math.round(math.max(math.sign(slope), 0)))     for x = 0 to 2         if not lr_showbrk or outofchannel != x or nz(outofchannel[1], -1) != -1             line.delete(array.get(reglines, x))         else             line.set_color(array.get(reglines, x), lr_brkcol)             line.set_width(array.get(reglines, x), 1)             line.set_style(array.get(reglines, x), line.style_dotted)             line.set_extend(array.get(reglines, x), extend.none)         float offset = dev * lr_dev * (x - 1)         array.set(reglines, x,              line.new(x1=bar_index - (lr_len - 1), y1=y1_ + offset, x2=bar_index, y2=y2_ + offset,                       color=cur_col, style=x % 2 == 1 ? line.style_solid : line.style_dashed, width=1,                       extend=lr_extend ? extend.right : extend.none))     if lr_fibo         for x = 0 to 3             line.delete(array.get(fibolines, x))             float fibo_off = -dev * lr_dev + dev * lr_dev * 2 * array.get(fibo_ratios, x)             array.set(fibolines, x,                  line.new(x1=bar_index - (lr_len - 1), y1=y1_ + fibo_off, x2=bar_index, y2=y2_ + fibo_off,                           color=color.new(cur_col, 50), style=line.style_dotted, width=1,                           extend=lr_extend ? extend.right : extend.none))     var label sidelab = label.new(bar_index - (lr_len - 1), y1_, "S", size=size.normal, style=label.style_none)     string txt        = slope > 0 ? (slope > slope[1] ? "⇑" : "⇗") : slope < 0 ? (slope < slope[1] ? "⇓" : "⇘") : "⇒"     color  cur_col_lbl = slope > 0 ? lr_upcol : slope < 0 ? lr_dncol : lr_brkcol     label.set_text(sidelab, txt)     label.set_x(sidelab, bar_index - (lr_len - 1))     label.set_y(sidelab, slope > 0 ? y1_ - dev * lr_dev : slope < 0 ? y1_ + dev * lr_dev : y1_)     label.set_textcolor(sidelab, cur_col_lbl)
Analisis Saham Potensial Indonesia
Analisis PNLF: Strategi Trading Institusional
Memperhalus Permintaan Pembayaran DP
Pemegang Saham dan Broker Emiten MINA
Stockbit: Strategi Follow Bandar
Analisis Saham NCKL: Strategi Institusional
Analisis Saham NCKL: Rekomendasi WNS
Analisis NCKL: Trading Plan Institusional
Mencari Garis Magnet Penarik Harga
Automated SnR Indicator Deep Dive
Memperbaiki Setup Trading Fibo dan VPVR
IHSG Tertekan, Strategi Portofolio
EMA Institusional: Angka Magic SNR
Analisis BRMS: Model Kuantitatif & Taktis
Prompts Pelatihan Screener Saham
Analisis ANTM: Strategi Trading Institusional
Expert Analysis of Dynamic RSI Indicator
Analisis Celah Indikator VIX Fix
Analisis Harga Proyek Mini-ERP
Menambahkan Fitur Gap Block Indikator
Perbaikan Surat Lamaran Kerja Staff IT
Analisis Teknikal Emiten BNBR Terbaru
Hotel Aliante Malang: Fasilitas & Ulasan
Benjolan Gusi: Penyebab dan Tindakan
Atasi Link Google Maps WhatsApp Error
Persiapan Tes PT Adicipta Inovasi Teknologi
Revisi Surat Lamaran IT Support IRASA
Mengenal Algobash: Platform Talent Assessment
Tanpa merubah wajah, fokus pada model rambut, karena jika sangat pendek rambut akan berdiri seperti duri², saya ingin model pendel seperti petinju bivol.
Kabel RCA: Putih, Merah, dan Fungsinya
Posisi Antena WiFi untuk Jangkauan Luas
Kemitraan Nescafe Container Malang
Acara dan Atraksi CKS Memorial Hall
Pengisian Form Pengalaman Proyek
Gemini Mengenali Data Pengguna
Bantuan Isi Formulir Rekrutmen AdIns
Alasan Kerja di Taiwan: Wawancara
Pernyataan Biodata Kerja Taiwan
Biaya Sertifikasi BNSP Kerja Taiwan
Perbaikan Visualisasi Tiga Dimensi
Perbaikan Layout Form HTML
Layup Drawer Canvas Implementation
Analisis Sentimen Komentar YouTube
Panduan Analisis Sentimen YouTube Python
Trik Cepat Psikotes Aritmatika
Tes Pabrik Taiwan Sparepart Otomotif
Coop TD Hell Abyss Formasi Hero
apakah kamu tau? Penerimaan Konsultan Individidu SNVT PJPA I BWS Kalimantan II Tahun Anggaran 2026
buat foto sedikit berpose untuk keperluan linkedin tapin jgn terlalu jauh hanya sedikit mundur saja agar tidak terlalu close up. dan formal, foto sangat sedikit agar terlihat informal santai. wajah rambut dll tetap sama.
Membuat Indikator Kustom TradingView
Skrip Video Perkenalan General IT
Pesan Blokir WhatsApp: Penjelasan Tampilan
Perubahan Tanggal Blokir WhatsApp
Bahaya Obat Mampet Diare, Solusi Sehat
Kode_1 Tersimpan: SMC, MA, Fibo
Mengatasi Router Advan Terdeteksi VPN
Coop TD Hell Mode Setup
Coop TD Hell Strategy Without Liberation
Laptop Gaming Ringan 12 Juta
foto saya rubah bajunya seperti baju yufra. sisanya muka jgn dirubah.
Komitmen Buku Kenangan S1 Lima Tahun
Deteksi Duplikasi File Perjanjian Sewa
Trading Strategy: SnR, VWAP, ADR
Memahami Kode Klasifikasi S&R
Modifikasi Dashboard S&R
Volume Profile: Deteksi Harga Bandar
Combining Trading Indicators
Pine Script Cleanup Loop Fix
Memahami Kode Indikator Trading
Persiapan Indikator Saham Day Trading
semua sama persis, logic, informasi dll, hanya saja style ui lebih tiny dan readble no simbol2. warna enak diliat. soft. jelas. // This work is licensed under CC BY-NC-SA 4.0 https://creativecommons.org/licenses/by-nc-sa/4.0/ // ADR IDX — Average Daily Range // Features: ADR · Empirical Probability · Daily Projection · Range Completion //           Historical Distribution · IDX Session · Multi-Period · Dashboard // Konsisten dengan SMC IDX v2, VP IDX, Super RSI IDX, Smart S&R IDX //@version=5 indicator("ADR IDX [Projection · Probability · Distribution]",           shorttitle="ADR IDX", overlay=true,           max_lines_count=200, max_boxes_count=50, max_labels_count=100) //============================================================================= // 1. SETTINGS //============================================================================= grp_adr   = "1. ADR Calculation" adr_len   = input.int(14,  "ADR Period (days)", minval=5, maxval=60,               tooltip="Jumlah hari untuk rata-rata. Default 14 hari = 2 minggu trading.", group=grp_adr) adr_len2  = input.int(30,  "ADR Period 2 (days)", minval=5, maxval=120,               tooltip="Period kedua untuk perbandingan.", group=grp_adr) adr_len3  = input.int(5,   "ADR Period 3 (days — Weekly avg)", minval=3, maxval=20, group=grp_adr) adr_method = input.string("True Range", "ADR Method",               options=["High-Low", "True Range"],               tooltip="High-Low: simpel. True Range: memperhitungkan gap antar hari.", group=grp_adr) grp_proj  = "2. Projection" show_proj  = input.bool(true,  "Show Daily Projection Lines", group=grp_proj) proj_from  = input.string("Open", "Project From",               options=["Open", "Previous Close", "Midnight Open"],               tooltip="Open: dari harga open hari ini.\nPrevious Close: dari close kemarin.",               group=grp_proj) show_50    = input.bool(true,  "Show 50% Level", inline="p1", group=grp_proj) show_100   = input.bool(true,  "Show 100% Level (Full ADR)", inline="p1", group=grp_proj) show_150   = input.bool(true,  "Show 150% Extension", inline="p2", group=grp_proj) show_200   = input.bool(false, "Show 200% Extension", inline="p2", group=grp_proj) grp_prob  = "3. Empirical Probability" prob_len  = input.int(100, "Probability Lookback (trading days)", minval=20, maxval=252,               tooltip="Jumlah hari historis untuk hitung distribusi empiris.\n100 = ~5 bulan.", group=grp_prob) show_prob = input.bool(true, "Show Probability Tiers", group=grp_prob) grp_ses   = "4. IDX Session" show_sess_line = input.bool(true, "Show Session Open/Close Lines", group=grp_ses) show_rvol  = input.bool(true, "Show RVOL (Relative Volume)", group=grp_ses) grp_vis   = "5. Display" show_dash  = input.bool(true, "Show Dashboard", group=grp_vis) show_hist  = input.bool(true, "Show Range History Bars (bottom strip)", group=grp_vis) dash_pos   = input.string("Top Right", "Dashboard Position",               options=["Top Right", "Top Left", "Bottom Right", "Bottom Left"], group=grp_vis) grp_col   = "6. Colors" col_bull   = input.color(#1976d2, "Bull Projection",  inline="c1", group=grp_col) col_bear   = input.color(#d32f2f, "Bear Projection",  inline="c1", group=grp_col) col_50     = input.color(color.new(#f57c00, 20), "50% Level",  inline="c2", group=grp_col) col_100    = input.color(color.new(#7c3aed, 20), "100% Level", inline="c2", group=grp_col) col_ext    = input.color(color.new(#d32f2f, 40), "Extension",  inline="c3", group=grp_col) col_comp   = input.color(color.new(#2e7d32, 0),  "Complete",   inline="c3", group=grp_col) col_text   = input.color(#37474f, "Text", group=grp_col) //============================================================================= // 2. TIMEFRAME GUARD // Indikator ini optimal di intraday (1m–1H). Jika di Daily+ tampilkan warning. //============================================================================= bool is_intraday = timeframe.isintraday bool is_daily    = timeframe.isdaily or timeframe.isweekly or timeframe.ismonthly //============================================================================= // 3. DAILY DATA REQUEST // Semua perhitungan ADR butuh data harian. //============================================================================= // Ambil OHLC harian [d_open, d_high, d_low, d_close, d_vol] = request.security(syminfo.tickerid, "D",      [open, high, low, close, volume],      lookahead=barmerge.lookahead_off) // Daily range per metode float d_range = adr_method == "True Range" ?      math.max(d_high - d_low, math.abs(d_high - d_close[1]), math.abs(d_low - d_close[1])) :      (d_high - d_low) // ADR kalkulasi (SMA dari daily range) float adr14  = request.security(syminfo.tickerid, "D", ta.sma(d_range, adr_len),   lookahead=barmerge.lookahead_off) float adr30  = request.security(syminfo.tickerid, "D", ta.sma(d_range, adr_len2),  lookahead=barmerge.lookahead_off) float adr5   = request.security(syminfo.tickerid, "D", ta.sma(d_range, adr_len3),  lookahead=barmerge.lookahead_off) // Daily volume SMA untuk RVOL float d_vol_sma = request.security(syminfo.tickerid, "D", ta.sma(d_vol, 20), lookahead=barmerge.lookahead_off) float d_rvol    = d_vol / math.max(d_vol_sma, 1.0) //============================================================================= // 4. CURRENT DAY TRACKING // Lacak intraday high, low, open dari bar chart (bukan daily request). //============================================================================= var float today_open  = na var float today_high  = na var float today_low   = na var int   today_start = na // Detect session open (new day) bool is_new_day = ta.change(time("D")) != 0 if is_new_day     today_open  := open     today_high  := high     today_low   := low     today_start := bar_index else     today_high := math.max(nz(today_high, high), high)     today_low  := math.min(nz(today_low, low), low) // Projection anchor float proj_anchor = proj_from == "Open"           ? nz(today_open, d_open) :proj_from == "Previous Close"  ? d_close[1] :nz(today_open, d_open)   // Midnight Open = same as open for IDX // Current day range completion float cur_range    = nz(today_high, high) - nz(today_low, low) float range_comp   = not na(adr14) and adr14 > 0 ? cur_range / adr14 * 100.0 : na // Intraday direction bias (close vs open) bool  day_bull     = close >= nz(today_open, close) float cur_move_up  = not na(today_open) ? close - today_open : na float cur_move_dn  = not na(today_open) ? today_open - close : na //============================================================================= // 5. EMPIRICAL PROBABILITY DISTRIBUTION // Hitung dari lookback hari historis: // Berapa % hari yang range-nya ≥ 50% / 80% / 100% / 120% / 150% ADR? // Ini adalah probabilitas empiris, bukan asumsi distribusi normal. //============================================================================= // Minta daily range historis via request.security float[] prob_ranges = array.new_float(0) // Kita hitung empiris dengan loop di daily bars // Pendekatan: simpan normalized range (range/ADR) per hari // Hitung di daily TF, kirim via security // Karena Pine terbatas, kita hitung langsung: // Untuk setiap threshold, hitung % hari yang melampaui threshold * ADR calc_prob_inner(float thresh) =>     int   count_all  = 0     int   count_hit  = 0     float adr_here   = ta.sma(d_range, adr_len)     for i = 1 to math.min(prob_len, 250)         float past_range = d_range[i]         if not na(past_range) and not na(adr_here[i]) and adr_here[i] > 0             count_all += 1             if past_range >= adr_here[i] * thresh                 count_hit += 1     count_all > 0 ? float(count_hit) / float(count_all) * 100.0 : na calc_prob_threshold(float thresh) =>     request.security(syminfo.tickerid,"D",calc_prob_inner(thresh),lookahead = barmerge.lookahead_off) // Hitung probabilitas empiris untuk 5 threshold float prob_50  = calc_prob_threshold(0.50) float prob_80  = calc_prob_threshold(0.80) float prob_100 = calc_prob_threshold(1.00) float prob_120 = calc_prob_threshold(1.20) float prob_150 = calc_prob_threshold(1.50) //============================================================================= // 6. PROJECTION LEVELS //============================================================================= float proj_up_50  = proj_anchor + adr14 * 0.50 float proj_up_100 = proj_anchor + adr14 * 1.00 float proj_up_150 = proj_anchor + adr14 * 1.50 float proj_up_200 = proj_anchor + adr14 * 2.00 float proj_dn_50  = proj_anchor - adr14 * 0.50 float proj_dn_100 = proj_anchor - adr14 * 1.00 float proj_dn_150 = proj_anchor - adr14 * 1.50 float proj_dn_200 = proj_anchor - adr14 * 2.00 //============================================================================= // 7. DRAWING — barstate.islast //============================================================================= var line[]  d_lines  = array.new_line(0) var label[] d_labels = array.new_label(0) var box[]   d_boxes  = array.new_box(0) fmt(float v)  => str.tostring(math.round(v), "#,###") fmtd(float v) => str.tostring(math.round(v, 1), "#.0") fmtp(float v) => fmtd(v) + "%" prob_color(p) =>     p >= 60.0 ? col_comp :p >= 40.0 ? color.rgb(245,124,0) :col_bear if barstate.islast and show_proj and is_intraday and not na(adr14) and not na(today_start)     // Cleanup     for ln in d_lines         line.delete(ln)     array.clear(d_lines)     for lb in d_labels         label.delete(lb)     array.clear(d_labels)     for bx in d_boxes         box.delete(bx)     array.clear(d_boxes)     int   x1    = nz(today_start, bar_index - 20)     int   x2    = bar_index + 30     float atr_c = ta.atr(14)     // ── Anchor (Open) line     array.push(d_lines, line.new(x1, proj_anchor, x2, proj_anchor,          color=color.new(col_text, 40), style=line.style_dashed, width=1))     array.push(d_labels, label.new(x2, proj_anchor, " Open " + fmt(proj_anchor),          color=color.new(color.white, 100), textcolor=color.new(col_text, 30),          style=label.style_none, size=size.small, yloc=yloc.price))     // ── BULLISH PROJECTIONS (above anchor)     if show_50         bool hit_50_up = not na(today_high) and today_high >= proj_up_50         color c50u = hit_50_up ? col_comp : col_50         array.push(d_lines, line.new(x1, proj_up_50, x2, proj_up_50,              color=c50u, style=line.style_dotted, width=1))         array.push(d_labels, label.new(x2, proj_up_50,              (hit_50_up ? "✓ " : "") + " +50%  " + fmt(proj_up_50) +              (show_prob ? "  P=" + fmtp(nz(prob_50, 0)) : ""),              color=color.new(color.white, 100), textcolor=c50u,              style=label.style_none, size=size.tiny, yloc=yloc.price))     if show_100         bool hit_100_up = not na(today_high) and today_high >= proj_up_100         color c100u = hit_100_up ? col_comp : col_100         array.push(d_lines, line.new(x1, proj_up_100, x2, proj_up_100,              color=c100u, style=line.style_solid, width=2))         array.push(d_labels, label.new(x2, proj_up_100,              (hit_100_up ? "✓ " : "") + " +ADR  " + fmt(proj_up_100) +              (show_prob ? "  P=" + fmtp(nz(prob_100, 0)) : ""),              color=color.new(color.white, 100), textcolor=c100u,              style=label.style_none, size=size.small, yloc=yloc.price))     if show_150         bool hit_150_up = not na(today_high) and today_high >= proj_up_150         color c150u = hit_150_up ? col_comp : col_ext         array.push(d_lines, line.new(x1, proj_up_150, x2, proj_up_150,              color=c150u, style=line.style_dashed, width=1))         array.push(d_labels, label.new(x2, proj_up_150,              (hit_150_up ? "✓ " : "") + " +150%  " + fmt(proj_up_150) +              (show_prob ? "  P=" + fmtp(nz(prob_150, 0)) : ""),              color=color.new(color.white, 100), textcolor=c150u,              style=label.style_none, size=size.tiny, yloc=yloc.price))     if show_200         array.push(d_lines, line.new(x1, proj_up_200, x2, proj_up_200,              color=color.new(col_ext, 60), style=line.style_dotted, width=1))         array.push(d_labels, label.new(x2, proj_up_200, " +200%  " + fmt(proj_up_200),              color=color.new(color.white, 100), textcolor=color.new(col_ext, 40),              style=label.style_none, size=size.tiny, yloc=yloc.price))     // ── BEARISH PROJECTIONS (below anchor)     if show_50         bool hit_50_dn = not na(today_low) and today_low <= proj_dn_50         color c50d = hit_50_dn ? col_comp : col_50         array.push(d_lines, line.new(x1, proj_dn_50, x2, proj_dn_50,              color=c50d, style=line.style_dotted, width=1))         array.push(d_labels, label.new(x2, proj_dn_50,              (hit_50_dn ? "✓ " : "") + " -50%  " + fmt(proj_dn_50),              color=color.new(color.white, 100), textcolor=c50d,              style=label.style_none, size=size.tiny, yloc=yloc.price))     if show_100         bool hit_100_dn = not na(today_low) and today_low <= proj_dn_100         color c100d = hit_100_dn ? col_comp : col_100         array.push(d_lines, line.new(x1, proj_dn_100, x2, proj_dn_100,              color=c100d, style=line.style_solid, width=2))         array.push(d_labels, label.new(x2, proj_dn_100,              (hit_100_dn ? "✓ " : "") + " -ADR  " + fmt(proj_dn_100),              color=color.new(color.white, 100), textcolor=c100d,              style=label.style_none, size=size.small, yloc=yloc.price))     if show_150         bool hit_150_dn = not na(today_low) and today_low <= proj_dn_150         color c150d = hit_150_dn ? col_comp : col_ext         array.push(d_lines, line.new(x1, proj_dn_150, x2, proj_dn_150,              color=c150d, style=line.style_dashed, width=1))         array.push(d_labels, label.new(x2, proj_dn_150,              (hit_150_dn ? "✓ " : "") + " -150%  " + fmt(proj_dn_150),              color=color.new(color.white, 100), textcolor=c150d,              style=label.style_none, size=size.tiny, yloc=yloc.price))     // ── Today's range box (visual progress)     if not na(today_high) and not na(today_low)         array.push(d_boxes, box.new(x1, today_high, bar_index, today_low,              border_color=color.new(day_bull ? col_bull : col_bear, 50),              bgcolor=color.new(day_bull ? col_bull : col_bear, 90)))     // ── Range completion label on current bar     if not na(range_comp)         color rc_col = range_comp >= 100.0 ? col_comp :                        range_comp >= 80.0  ? col_100  :                        range_comp >= 50.0  ? col_50   : col_text         array.push(d_labels, label.new(bar_index, day_bull ? today_high : today_low,              fmtp(range_comp) + " complete",              color=color.new(color.white, 100), textcolor=rc_col,              style=label.style_none, size=size.tiny,              yloc=day_bull ? yloc.abovebar : yloc.belowbar))     // ── Session lines     if show_sess_line and not na(today_start) and not na(today_open)         // Vertical session open marker         array.push(d_lines, line.new(today_start, today_open - atr_c * 2,              today_start, today_open + atr_c * 2,              color=color.new(col_text, 50), style=line.style_solid, width=1))         array.push(d_labels, label.new(today_start, today_open + atr_c * 2.2,              "IDX Open",              color=color.new(color.white, 100), textcolor=color.new(col_text, 30),              style=label.style_none, size=size.tiny, yloc=yloc.price)) //============================================================================= // 8. DASHBOARD //============================================================================= table_pos() =>     dash_pos == "Top Left"     ? position.top_left    :dash_pos == "Bottom Right" ? position.bottom_right :dash_pos == "Bottom Left"  ? position.bottom_left  :position.top_right var table dash = table.new(table_pos(), 3, 18,      bgcolor=color.new(color.white, 92),      border_width=1, border_color=color.new(color.gray, 83),      frame_width=1,  frame_color=color.new(color.gray, 83)) if barstate.islast and show_dash     // ── HEADER     table.cell(dash, 0, 0, " ADR IDX", text_color=#f57c00,          text_size=size.small, text_halign=text.align_left,          bgcolor=color.new(#f57c00, 88))     table.cell(dash, 1, 0, " Daily Range Stats", text_color=#f57c00,          text_size=size.small, text_halign=text.align_center,          bgcolor=color.new(#f57c00, 88))     table.cell(dash, 2, 0, syminfo.ticker + " ", text_color=#f57c00,          text_size=size.small, text_halign=text.align_right,          bgcolor=color.new(#f57c00, 88))     // ── ADR VALUES     table.cell(dash, 0, 1, " ADR " + str.tostring(adr_len) + "d",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 1, (not na(adr14) ? fmt(adr14) : "—") + " pts ",          text_color=#f57c00, text_size=size.small, text_halign=text.align_right)     float adr14_pct = not na(adr14) and not na(close) ? adr14 / close * 100.0 : na     table.cell(dash, 2, 1, (not na(adr14_pct) ? fmtp(adr14_pct) : "—") + " ",          text_color=col_text, text_size=size.tiny, text_halign=text.align_right)     table.cell(dash, 0, 2, " ADR " + str.tostring(adr_len2) + "d",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 2, (not na(adr30) ? fmt(adr30) : "—") + " pts ",          text_color=color.new(#f57c00, 20), text_size=size.small, text_halign=text.align_right)     // Trend: expanding or contracting range?     string range_trend = (not na(adr14) and not na(adr30)) ?          (adr14 > adr30 ? "Expanding ↑" : adr14 < adr30 ? "Contracting ↓" : "Stable →") : "—"     color rt_col = (not na(adr14) and not na(adr30)) ?          (adr14 > adr30 ? col_bull : adr14 < adr30 ? col_bear : col_text) : col_text     table.cell(dash, 2, 2, range_trend + " ",          text_color=rt_col, text_size=size.tiny, text_halign=text.align_right)     table.cell(dash, 0, 3, " ADR " + str.tostring(adr_len3) + "d (Short)",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 3, (not na(adr5) ? fmt(adr5) : "—") + " pts ",          text_color=color.new(#f57c00, 40), text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 3, "", text_color=col_text, text_size=size.tiny)     // ── TODAY'S STATS     table.cell(dash, 0, 4, " ── Today ──",          text_color=color.new(col_text, 40), text_size=size.tiny, text_halign=text.align_left)     table.cell(dash, 1, 4, "", text_color=col_text, text_size=size.tiny)     table.cell(dash, 2, 4, "", text_color=col_text, text_size=size.tiny)     float today_range = not na(today_high) and not na(today_low) ? today_high - today_low : na     table.cell(dash, 0, 5, " Today Range",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 5, (not na(today_range) ? fmt(today_range) : "—") + " pts ",          text_color=day_bull ? col_bull : col_bear,          text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 5, (not na(range_comp) ? fmtp(range_comp) : "—") + " ",          text_color=range_comp >= 100.0 ? col_comp : col_text,          text_size=size.small, text_halign=text.align_right)     // Range completion bar     string comp_bar = ""     if not na(range_comp)         int filled = math.min(int(range_comp / 10.0), 10)         for b = 1 to 10             comp_bar := comp_bar + (b <= filled ? "█" : "░")     table.cell(dash, 0, 6, " Completion",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 6, comp_bar + " ",          text_color=range_comp >= 100.0 ? col_comp : range_comp >= 80.0 ? col_100 : col_50,          text_size=size.tiny, text_halign=text.align_right)     string comp_status = range_comp >= 150.0 ? "EXTENDED ⚡" :                          range_comp >= 100.0 ? "COMPLETE ✓" :                          range_comp >= 80.0  ? "Near Full" :                          range_comp >= 50.0  ? "Half Done" : "Early"     color comp_sc = range_comp >= 150.0 ? col_ext :range_comp >= 100.0 ? col_comp :range_comp >= 80.0  ? col_100 : col_text     table.cell(dash, 2, 6, comp_status + " ",          text_color=comp_sc, text_size=size.tiny, text_halign=text.align_right)     // Projection levels     table.cell(dash, 0, 7, " Proj +ADR",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 7, (not na(proj_up_100) ? fmt(proj_up_100) : "—") + " ",          text_color=col_bull, text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 7, (not na(proj_dn_100) ? fmt(proj_dn_100) : "—") + " ",          text_color=col_bear, text_size=size.small, text_halign=text.align_right)     // RVOL     if show_rvol         table.cell(dash, 0, 8, " Vol RVOL",              text_color=col_text, text_size=size.small, text_halign=text.align_left)         color rvol_col = d_rvol >= 2.0 ? col_comp : d_rvol >= 1.3 ? #f57c00 : col_text         string rvol_txt = not na(d_rvol) ? fmtd(d_rvol) + "×" : "—"         string rvol_st  = d_rvol >= 2.0 ? " HIGH" : d_rvol >= 1.3 ? " Above avg" : " Normal"         table.cell(dash, 1, 8, rvol_txt + " ",              text_color=rvol_col, text_size=size.small, text_halign=text.align_right)         table.cell(dash, 2, 8, rvol_st + " ",              text_color=rvol_col, text_size=size.tiny, text_halign=text.align_right)     // ── PROBABILITY SECTION     table.cell(dash, 0, 9, " ── Empirical Prob ──",          text_color=color.new(col_text, 40), text_size=size.tiny, text_halign=text.align_left)     table.cell(dash, 1, 9, str.tostring(prob_len) + " day sample ",          text_color=color.new(col_text, 40), text_size=size.tiny, text_halign=text.align_right)     table.cell(dash, 2, 9, "", text_color=col_text, text_size=size.tiny)     // P(≥50%)     table.cell(dash, 0, 10, " P(≥ 50% ADR)",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 10, (not na(prob_50) ? fmtp(prob_50) : "—") + " ",          text_color=not na(prob_50) ? prob_color(prob_50) : col_text,          text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 10, not na(prob_50) ? (prob_50 >= 70 ? "HIGH ▲" : prob_50 >= 40 ? "MED" : "LOW") + " " : "— ",          text_color=not na(prob_50) ? prob_color(prob_50) : col_text,          text_size=size.tiny, text_halign=text.align_right)     // P(≥80%)     table.cell(dash, 0, 11, " P(≥ 80% ADR)",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 11, (not na(prob_80) ? fmtp(prob_80) : "—") + " ",          text_color=not na(prob_80) ? prob_color(prob_80) : col_text,          text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 11, "", text_color=col_text, text_size=size.tiny)     // P(≥100%)     table.cell(dash, 0, 12, " P(≥ 100% ADR)",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 12, (not na(prob_100) ? fmtp(prob_100) : "—") + " ",          text_color=not na(prob_100) ? prob_color(prob_100) : col_text,          text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 12, "", text_color=col_text, text_size=size.tiny)     // P(≥120%)     table.cell(dash, 0, 13, " P(≥ 120% ADR)",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 13, (not na(prob_120) ? fmtp(prob_120) : "—") + " ",          text_color=not na(prob_120) ? prob_color(prob_120) : col_text,          text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 13, "", text_color=col_text, text_size=size.tiny)     // P(≥150%)     table.cell(dash, 0, 14, " P(≥ 150% ADR)",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 14, (not na(prob_150) ? fmtp(prob_150) : "—") + " ",          text_color=not na(prob_150) ? prob_color(prob_150) : col_text,          text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 14, "", text_color=col_text, text_size=size.tiny)     // ── SIGNAL / CONTEXT     table.cell(dash, 0, 15, " ── Context ──",          text_color=color.new(col_text, 40), text_size=size.tiny, text_halign=text.align_left)     table.cell(dash, 1, 15, "", text_color=col_text, text_size=size.tiny)     table.cell(dash, 2, 15, "", text_color=col_text, text_size=size.tiny)     // Range vs ADR tiers context     string ctx_txt = na     color  ctx_col = col_text     if not na(range_comp)         if range_comp < 30.0             ctx_txt := "Range sangat kecil — early session / range day"             ctx_col := color.new(col_text, 20)         else if range_comp < 60.0             ctx_txt := "Range berkembang — masih ada ruang bergerak"             ctx_col := col_50         else if range_comp < 90.0             ctx_txt := "Range besar — level ADR sudah dekat"             ctx_col := col_100         else if range_comp < 120.0             ctx_txt := "Full ADR tercapai — hati-hati reversal"             ctx_col := col_comp         else             ctx_txt := "Extension zone — range luar biasa hari ini"             ctx_col := col_ext     table.cell(dash, 0, 16, " Status",          text_color=col_text, text_size=size.small, text_halign=text.align_left)     table.cell(dash, 1, 16, (not na(ctx_txt) ? ctx_txt : "—") + " ",          text_color=ctx_col, text_size=size.small, text_halign=text.align_right)     table.cell(dash, 2, 16, "", text_color=col_text, text_size=size.tiny)     // TF warning     if not is_intraday         table.cell(dash, 0, 17, " ⚠ TF Warning",              text_color=col_bear, text_size=size.small, text_halign=text.align_left,              bgcolor=color.new(col_bear, 90))         table.cell(dash, 1, 17, "Switch to intraday TF ",              text_color=col_bear, text_size=size.small, text_halign=text.align_right,              bgcolor=color.new(col_bear, 90))         table.cell(dash, 2, 17, "for projections ",              text_color=col_bear, text_size=size.tiny, text_halign=text.align_right,              bgcolor=color.new(col_bear, 90))
Menambah Fitur Indikator Fibonacci Trading
ini indikator 1: // This work is licensed under CC BY-NC-SA 4.0 https://creativecommons.org/licenses/by-nc-sa/4.0/ // SMC Master IDX — Fixed & Optimized for Bursa Efek Indonesia // Fixes: Fakeout logic, LinReg channel formula, OB Strength, null safety PDH/PDL/PWH/PWL //@version=5 indicator("SMC IDX [Structure, MSS, Liquidity, Valuation & Channel]", overlay=true, max_lines_count=500, max_boxes_count=500, max_labels_count=500) //============================================================================= // 1. SETTINGS & UI STYLING //============================================================================= // --- SMC Structure Settings --- grp_str    = "1. Market Structure (BOS/CHoCH/MSS)" length     = input.int(5, "Pivots Lookback", minval=3, group=grp_str) show_lbl   = input.bool(true, "Show HH/LL Labels", inline="str1", group=grp_str) show_bos   = input.bool(true, "Show BOS/CHoCH/MSS", inline="str1", group=grp_str) mss_filter = input.bool(true, "MSS Filter (Body Close)", tooltip="MSS hanya valid jika candle close di luar structure.", group=grp_str) // --- Order Block Settings --- grp_ob     = "2. Order Block (Institutional Candles)" showBull   = input.int(3, 'Show Last Bullish OBs', minval=0, inline="ob1", group=grp_ob) showBear   = input.int(3, 'Show Last Bearish OBs', minval=0, inline="ob1", group=grp_ob) useBody    = input.bool(true, 'Use Candle Body for OB', inline="ob2", group=grp_ob) showObStr  = input.bool(true, 'Show OB Strength (%)', inline="ob2", group=grp_ob) // --- FVG Settings --- grp_fvg    = "3. Fair Value Gaps (Imbalance)" show_fvg   = input.bool(true, "Show FVG", inline="fvg1", group=grp_fvg) fvg_extend = input.int(5, "Extend FVG Boxes", inline="fvg1", group=grp_fvg) // --- Valuation --- grp_val    = "4. Valuation (Premium vs Discount)" show_eq    = input.bool(true, "Show Equilibrium (50%)", group=grp_val) // --- Liquidity Statistics Settings --- grp_ls       = "5. Statistical Liquidity (Probability)" ls_length    = input.int(10, 'Liquidity Lookback', minval=3, inline="ls1", group=grp_ls) ls_threshold = input.float(1.5, 'Volume Strength (RVOL)', step=0.1, inline="ls1", group=grp_ls) ls_eq_tol    = input.float(0.1, 'EQH/EQL Tolerance (ATR)', step=0.05, inline="ls2", group=grp_ls) ls_max_back  = input.int(20, 'Max Active Swings', inline="ls2", group=grp_ls) ls_conf_bars = input.int(2, "Fakeout Conf. Bars", minval=1, group=grp_ls) // --- Daily & Weekly Levels --- grp_dl      = "6. External Liquidity (Daily & Weekly)" show_daily  = input.bool(true, "Show PDH/PDL", inline="dl1", group=grp_dl) show_weekly = input.bool(true, "Show PWH/PWL", inline="dl1", group=grp_dl) // --- Linear Regression Channel Settings --- grp_lr     = "7. Linear Regression Channel (Statistics)" show_lr    = input.bool(true, "Show LinReg Channel", inline="lr1", group=grp_lr) lr_src     = input.source(close, "Source", inline="lr1", group=grp_lr) lr_len     = input.int(100, "Length", minval=10, inline="lr2", group=grp_lr) lr_dev     = input.float(2.0, "Deviation", minval=0.1, step=0.1, inline="lr2", group=grp_lr) lr_extend  = input.bool(true, "Extend Lines", inline="lr3", group=grp_lr) lr_fibo    = input.bool(false, "Show Fibonacci", inline="lr3", group=grp_lr) lr_showbrk = input.bool(true, "Show Broken Channel", group=grp_lr) // --- Colors --- grp_col = "8. Colors & Styling" col_bull     = input.color(#1976d2, "Bullish Str", inline="c_str", group=grp_col) col_bear     = input.color(#d32f2f, "Bearish Str", inline="c_str", group=grp_col) col_mss      = input.color(#7c3aed, "MSS", inline="c_str", group=grp_col) col_text     = input.color(#37474f, "Gen Text", inline="c_gen", group=grp_col) col_eq       = input.color(#7e57c2, "EQ (50%)", inline="c_gen", group=grp_col) bullCss      = input.color(color.new(#00897b, 85), 'Bull OB', inline='c_ob1', group=grp_col) bullBreakCss = input.color(color.new(#f57c00, 85), 'Bull Brk', inline='c_ob1', group=grp_col) bearCss      = input.color(color.new(#d32f2f, 85), 'Bear OB', inline='c_ob2', group=grp_col) bearBreakCss = input.color(color.new(#f57c00, 85), 'Bear Brk', inline='c_ob2', group=grp_col) fvg_bull_css = input.color(color.new(#4caf50, 85), "Bull FVG", inline="c_fvg", group=grp_col) fvg_bear_css = input.color(color.new(#ff5252, 85), "Bear FVG", inline="c_fvg", group=grp_col) ls_col_h     = input.color(color.new(#ef5350, 40), "Liq High", inline="c_ls1", group=grp_col) ls_col_l     = input.color(color.new(#26a69a, 40), "Liq Low", inline="c_ls1", group=grp_col) ls_col_eq    = input.color(color.new(#f9a825, 0), "EQH/EQL", inline="c_ls2", group=grp_col) ls_col_taken = input.color(color.new(#546e7a, 40), "Liq Taken", inline="c_ls2", group=grp_col) col_pdh      = input.color(#424242, "PDH/PDL", inline="c_ext", group=grp_col) col_pwh      = input.color(#000000, "PWH/PWL", inline="c_ext", group=grp_col) lr_upcol     = input.color(color.new(#1976d2, 30), "LR Up", inline="c_lr", group=grp_col) lr_dncol     = input.color(color.new(#d32f2f, 30), "LR Down", inline="c_lr", group=grp_col) lr_brkcol    = input.color(color.new(#546e7a, 40), "LR Broken", inline="c_lr", group=grp_col) var line[] ob_lines_array  = array.new_line() var box[]  ob_boxes_array  = array.new_box() var box[]  fvg_boxes_array = array.new_box() //============================================================================= // 2. HELPER FUNCTIONS & TYPES //============================================================================= type ob     float top       = na     float btm       = na     int   loc       = na   // timestamp (xloc.bar_time)     bool  breaker   = false     int   break_loc = na   // timestamp saat breaker terbentuk     float strength  = na type swing     float y       = na     int   x       = na     bool  crossed = false type liq_point     float price     float vol_strength     float raw_vol     bool  is_broken     int   break_idx     line  ln     label lbl     bool  is_eq     label lbl_sweep     bool  is_swept calc_ob_strength(float top, float btm, float vol, float avg_vol, float atr14) =>     float candle_size = math.max(top - btm, syminfo.mintick)     float size_factor = math.min(candle_size / math.max(atr14 * 2.0, syminfo.mintick), 1.0)     float vol_factor  = avg_vol > 0 ? math.min(vol / (avg_vol * 2.5), 1.0) : 0.5     math.round((size_factor * 0.5 + vol_factor * 0.5) * 100, 1) swings(len) =>     var int   os  = 0     var swing top = swing.new(na, na)     var swing btm = swing.new(na, na)     upper = ta.highest(len)     lower = ta.lowest(len)     os   := high[len] > upper ? 0 : low[len] < lower ? 1 : os     if os == 0 and os[1] != 0         top := swing.new(high[len], bar_index[len])     if os == 1 and os[1] != 1         btm := swing.new(low[len], bar_index[len])     [top, btm] method display(ob id, css, break_css, show_str) =>     string txt_str = (show_str and not na(id.strength)) ? str.tostring(id.strength) + "%" : ""     if id.breaker         b1 = box.new(id.loc, id.top, id.break_loc, id.btm, border_color=css, bgcolor=css, xloc=xloc.bar_time)         b2 = box.new(id.break_loc, id.top, time + 1, id.btm, border_color=break_css, bgcolor=break_css, extend=extend.none, xloc=xloc.bar_time, text=txt_str, text_color=col_text, text_size=size.tiny, text_halign=text.align_right)         array.push(ob_boxes_array, b1)         array.push(ob_boxes_array, b2)     else         b1 = box.new(id.loc, id.top, time, id.btm, border_color=css, bgcolor=css, extend=extend.none, xloc=xloc.bar_time, text=txt_str, text_color=col_text, text_size=size.tiny, text_halign=text.align_right)         array.push(ob_boxes_array, b1) //============================================================================= // 3. MARKET STRUCTURE LOGIC //============================================================================= ph = ta.pivothigh(length, length) pl = ta.pivotlow(length,  length) float atr_gap = ta.atr(14) * 0.8 var int   trend      = 0 var float prev_ph    = na var float prev_pl    = na var float top_struct = na var float btm_struct = na bool   bull_break = false bool   bear_break = false string txt_break  = na color  col_break  = na if not na(prev_ph)     bool b_wick  = ta.crossover(high, prev_ph)     bool b_body  = ta.crossover(close, prev_ph)     bool b_valid = mss_filter ? b_body : b_wick     if b_valid         if trend != 1             bull_break := true             trend      := 1             bool is_strong = b_body             txt_break  := is_strong ? "MSS" : "CHoCH"             col_break  := is_strong ? col_mss : col_bull             line.new(bar_index, close, bar_index, prev_ph, color=col_break, style=line.style_solid, width=is_strong ? 2 : 1)         else             bull_break := true             txt_break  := "BOS"             col_break  := col_bull             line.new(bar_index, close, bar_index, prev_ph, color=col_break, style=line.style_solid, width=1) if not na(prev_pl)     bool b_wick  = ta.crossunder(low, prev_pl)     bool b_body  = ta.crossunder(close, prev_pl)     bool b_valid = mss_filter ? b_body : b_wick     if b_valid         if trend != -1             bear_break := true             trend      := -1             bool is_strong = b_body             txt_break  := is_strong ? "MSS" : "CHoCH"             col_break  := is_strong ? col_mss : col_bear             line.new(bar_index, close, bar_index, prev_pl, color=col_break, style=line.style_solid, width=is_strong ? 2 : 1)         else             bear_break := true             txt_break  := "BOS"             col_break  := col_bear             line.new(bar_index, close, bar_index, prev_pl, color=col_break, style=line.style_solid, width=1) if show_bos     if bull_break         label.new(bar_index, high + atr_gap, txt_break, color=color.new(color.white, 100), textcolor=col_break, style=label.style_none, size=size.tiny, yloc=yloc.price)     if bear_break         label.new(bar_index, low  - atr_gap, txt_break, color=color.new(color.white, 100), textcolor=col_break, style=label.style_none, size=size.tiny, yloc=yloc.price) if not na(ph)     prev_ph := ph     string txt = "H"     if not na(top_struct)         txt := ph > top_struct ? "HH" : "LH"     top_struct := ph     if show_lbl         label.new(bar_index[length], na, txt, color=color.new(color.white, 100), textcolor=col_text, style=label.style_none, size=size.tiny, yloc=yloc.abovebar) if not na(pl)     prev_pl := pl     string txt = "L"     if not na(btm_struct)         txt := pl < btm_struct ? "LL" : "HL"     btm_struct := pl     if show_lbl         label.new(bar_index[length], na, txt, color=color.new(color.white, 100), textcolor=col_text, style=label.style_none, size=size.tiny, yloc=yloc.belowbar) //============================================================================= // 4. PRECISION ORDER BLOCKS //============================================================================= n_idx = bar_index [top_sw, btm_sw] = swings(length) float vol_sma20 = ta.sma(volume, 20) float atr14     = ta.atr(14) // Bullish OB var bullish_ob = array.new<ob>(0) if close > top_sw.y and not top_sw.crossed     top_sw.crossed := true     float lowest_val = low[1]     int   lowest_idx = 1     int loop_limit   = math.min(n_idx - top_sw.x, 100)     for i = 1 to loop_limit         if low[i] < lowest_val             lowest_val := low[i]             lowest_idx := i     int ob_idx = lowest_idx     if close[lowest_idx] > open[lowest_idx]         if (lowest_idx + 1) < bar_index and close[lowest_idx + 1] < open[lowest_idx + 1]             ob_idx := lowest_idx + 1     float ob_top  = useBody ? math.max(open[ob_idx], close[ob_idx]) : high[ob_idx]     float ob_btm  = useBody ? math.min(open[ob_idx], close[ob_idx]) : low[ob_idx]     int   ob_time = time[ob_idx]     float ob_vol  = volume[ob_idx]     float avg_vol = nz(vol_sma20[ob_idx], vol_sma20)     float str_val = calc_ob_strength(ob_top, ob_btm, ob_vol, avg_vol, nz(atr14[ob_idx], atr14))     bullish_ob.unshift(ob.new(ob_top, ob_btm, ob_time, false, na, str_val)) if bullish_ob.size() > 0     for i = bullish_ob.size() - 1 to 0         element = bullish_ob.get(i)         if not element.breaker             if close < element.btm                 element.breaker   := true                 element.break_loc := time         else             if close > element.top                 bullish_ob.remove(i) // Bearish OB var bearish_ob = array.new<ob>(0) if close < btm_sw.y and not btm_sw.crossed     btm_sw.crossed := true     float highest_val = high[1]     int   highest_idx = 1     int loop_limit    = math.min(n_idx - btm_sw.x, 100)     for i = 1 to loop_limit         if high[i] > highest_val             highest_val := high[i]             highest_idx := i     int ob_idx = highest_idx     if close[highest_idx] < open[highest_idx]         if (highest_idx + 1) < bar_index and close[highest_idx + 1] > open[highest_idx + 1]             ob_idx := highest_idx + 1     float ob_top  = useBody ? math.max(open[ob_idx], close[ob_idx]) : high[ob_idx]     float ob_btm  = useBody ? math.min(open[ob_idx], close[ob_idx]) : low[ob_idx]     int   ob_time = time[ob_idx]     float ob_vol  = volume[ob_idx]     float avg_vol = nz(vol_sma20[ob_idx], vol_sma20)     float str_val = calc_ob_strength(ob_top, ob_btm, ob_vol, avg_vol, nz(atr14[ob_idx], atr14))     bearish_ob.unshift(ob.new(ob_top, ob_btm, ob_time, false, na, str_val)) if bearish_ob.size() > 0     for i = bearish_ob.size() - 1 to 0         element = bearish_ob.get(i)         if not element.breaker             if close > element.top                 element.breaker   := true                 element.break_loc := time         else             if close < element.btm                 bearish_ob.remove(i) //============================================================================= // 5. FAIR VALUE GAPS //============================================================================= if show_fvg     if low > high[2] and close[1] > high[2]         fvg_box = box.new(bar_index - 2, low,  bar_index + fvg_extend, high[2], border_color=na, bgcolor=fvg_bull_css)         array.push(fvg_boxes_array, fvg_box)     if high < low[2] and close[1] < low[2]         fvg_box = box.new(bar_index - 2, high, bar_index + fvg_extend, low[2],  border_color=na, bgcolor=fvg_bear_css)         array.push(fvg_boxes_array, fvg_box)     if array.size(fvg_boxes_array) > 50         old_fvg = array.remove(fvg_boxes_array, 0)         box.delete(old_fvg) //============================================================================= // 6. VALUATION: PREMIUM / DISCOUNT (SMART RANGE LOGIC + MINIMALIST UI) //============================================================================= var float valid_dh = na var float valid_dl = na var float pending_origin = na var bool  wait_for_ph = false var bool  wait_for_pl = false // 1. Jika ada Bullish Break, rekam Swing Low terakhir if bull_break     pending_origin := btm_struct     wait_for_ph := true     wait_for_pl := false // 2. Jika ada Bearish Break, rekam Swing High terakhir if bear_break     pending_origin := top_struct     wait_for_pl := true     wait_for_ph := false // 3. Kunci range HANYA JIKA Swing baru (ujung impuls) sudah terkonfirmasi if not na(ph) and wait_for_ph     valid_dh := ph     valid_dl := pending_origin     wait_for_ph  := false if not na(pl) and wait_for_pl     valid_dl := pl     valid_dh := pending_origin     wait_for_pl  := false var line  dh_line = na var label dh_lbl  = na var line  eq_line = na var label eq_lbl  = na var line  dl_line = na var label dl_lbl  = na if show_eq     line.delete(dh_line),  label.delete(dh_lbl)     line.delete(eq_line),  label.delete(eq_lbl)     line.delete(dl_line),  label.delete(dl_lbl)     // Pastikan range valid dan memiliki jarak     if not na(valid_dh) and not na(valid_dl) and valid_dh != valid_dl         float mid_price = (valid_dh + valid_dl) / 2                 // Jangkar visual dimulai dari letak pivot terbentuk (bar_index - length)         int start_idx   = bar_index - length         int end_idx     = bar_index + 12         // Garis Deal High (Premium)         dh_line := line.new(start_idx, valid_dh, end_idx, valid_dh, color=color.new(col_eq, 60), style=line.style_solid, width=1)         dh_lbl  := label.new(end_idx, valid_dh, " Premium", color=color.new(color.white, 100), textcolor=color.new(col_text, 20), style=label.style_none, size=size.small)         // Garis Equilibrium (50%)         eq_line := line.new(start_idx, mid_price, end_idx, mid_price, color=color.new(col_eq, 20), style=line.style_dotted, width=1)         eq_lbl  := label.new(end_idx, mid_price, " EQ 50%", color=color.new(color.white, 100), textcolor=color.new(col_eq, 0), style=label.style_none, size=size.small)         // Garis Deal Low (Discount)         dl_line := line.new(start_idx, valid_dl, end_idx, valid_dl, color=color.new(col_eq, 60), style=line.style_solid, width=1)         dl_lbl  := label.new(end_idx, valid_dl, " Discount", color=color.new(color.white, 100), textcolor=color.new(col_text, 20), style=label.style_none, size=size.small) //============================================================================= // 7. EXTERNAL LIQUIDITY — IDX DAILY & WEEKLY //============================================================================= var float cur_d_h = na, var float cur_d_l = na var float pdh     = na, var float pdl     = na var int   cur_d_start = na if ta.change(time("D"))     pdh         := cur_d_h     pdl         := cur_d_l     cur_d_h     := high     cur_d_l     := low     cur_d_start := bar_index else     cur_d_h := math.max(nz(cur_d_h, high), high)     cur_d_l := math.min(nz(cur_d_l, low), low) var float cur_w_h = na, var float cur_w_l = na var float pwh     = na, var float pwl     = na var int   cur_w_start = na if ta.change(time("W"))     pwh         := cur_w_h     pwl         := cur_w_l     cur_w_h     := high     cur_w_l     := low     cur_w_start := bar_index else     cur_w_h := math.max(nz(cur_w_h, high), high)     cur_w_l := math.min(nz(cur_w_l, low), low) float final_pdh = not na(pdh) ? pdh : cur_d_h float final_pdl = not na(pdl) ? pdl : cur_d_l bool  is_friday_close = dayofweek == dayofweek.friday and session.islastbar_regular float final_pwh = is_friday_close ? cur_w_h : (not na(pwh) ? pwh : cur_w_h) float final_pwl = is_friday_close ? cur_w_l : (not na(pwl) ? pwl : cur_w_l) var line  l_pdh = na, var line  l_pdl = na var label lbl_pdh = na, var label lbl_pdl = na var line  l_pwh = na, var line  l_pwl = na var label lbl_pwh = na, var label lbl_pwl = na if show_daily and not na(final_pdh) and not na(final_pdl)     line.delete(l_pdh),    line.delete(l_pdl)     label.delete(lbl_pdh), label.delete(lbl_pdl)     int anchor_d   = nz(cur_d_start, bar_index - 20)     int right_ex_d = bar_index + 16     l_pdh   := line.new(anchor_d, final_pdh, right_ex_d, final_pdh, color=color.new(col_pdh, 30), style=line.style_dashed, width=1)     lbl_pdh := label.new(right_ex_d, final_pdh, " PDH", color=color.new(color.white, 100), textcolor=col_pdh, style=label.style_none, size=size.small)     l_pdl   := line.new(anchor_d, final_pdl, right_ex_d, final_pdl, color=color.new(col_pdh, 30), style=line.style_dashed, width=1)     lbl_pdl := label.new(right_ex_d, final_pdl, " PDL", color=color.new(color.white, 100), textcolor=col_pdh, style=label.style_none, size=size.small) if show_weekly and not na(final_pwh) and not na(final_pwl)     line.delete(l_pwh),    line.delete(l_pwl)     label.delete(lbl_pwh), label.delete(lbl_pwl)     int anchor_w   = nz(cur_w_start, bar_index - 100)     int right_ex_w = bar_index + 24     l_pwh   := line.new(anchor_w, final_pwh, right_ex_w, final_pwh, color=color.new(col_pwh, 20), style=line.style_dotted, width=1)     lbl_pwh := label.new(right_ex_w, final_pwh, " PWH", color=color.new(color.white, 100), textcolor=col_pwh, style=label.style_none, size=size.small)     l_pwl   := line.new(anchor_w, final_pwl, right_ex_w, final_pwl, color=color.new(col_pwh, 20), style=line.style_dotted, width=1)     lbl_pwl := label.new(right_ex_w, final_pwl, " PWL", color=color.new(color.white, 100), textcolor=col_pwh, style=label.style_none, size=size.small) //============================================================================= // 8. STATISTICAL LIQUIDITY (INTERNAL) //============================================================================= format_vol_liq(float v) =>     v >= 1000000 ? str.format("{0,number,#.#}M", v / 1000000) :      v >= 1000   ? str.format("{0,number,#.#}K", v / 1000)    :      str.tostring(v, "#") calc_rvol() =>     float avg_vol = ta.sma(volume, 50)     volume / math.max(avg_vol, 1.0) float atr_val = ta.atr(14) var liq_point[] arr_highs = array.new<liq_point>(0) var liq_point[] arr_lows  = array.new<liq_point>(0) float ls_ph_val = ta.pivothigh(ls_length, ls_length) float ls_pl_val = ta.pivotlow(ls_length,  ls_length) if not na(ls_ph_val)     float swing_rvol = calc_rvol()[ls_length]     float raw_v      = volume[ls_length]     if swing_rvol >= ls_threshold or (high[ls_length] - low[ls_length]) > atr_val         bool found_eqh = false         if array.size(arr_highs) > 0             for i = 0 to array.size(arr_highs) - 1                 liq_point prev_p = array.get(arr_highs, i)                 if math.abs(ls_ph_val - prev_p.price) < (atr_val * ls_eq_tol) and not prev_p.is_broken                     found_eqh := true                     line.set_color(prev_p.ln, ls_col_eq)                     line.set_style(prev_p.ln, line.style_dashed)                     label.set_text(prev_p.lbl, "EQH (" + format_vol_liq(prev_p.raw_vol) + ")")                     label.set_textcolor(prev_p.lbl, ls_col_eq)                     prev_p.is_eq := true                     break         color  fin_col  = found_eqh ? ls_col_eq : ls_col_h         string base_txt = found_eqh ? "EQH" : "BSL"         string full_txt = base_txt + " (" + format_vol_liq(raw_v) + ")"         line  new_ln  = line.new(bar_index[ls_length], ls_ph_val, bar_index, ls_ph_val, color=fin_col, style=found_eqh ? line.style_dashed : line.style_solid, width=1)         label new_lbl = label.new(bar_index, ls_ph_val, full_txt, color=color.new(color.white, 100), style=label.style_none, size=size.tiny, textcolor=col_text, yloc=yloc.price)         array.unshift(arr_highs, liq_point.new(ls_ph_val, swing_rvol, raw_v, false, na, new_ln, new_lbl, found_eqh, na, false))         if array.size(arr_highs) > ls_max_back             liq_point old = array.pop(arr_highs)             line.delete(old.ln),  label.delete(old.lbl)             if not na(old.lbl_sweep)                 label.delete(old.lbl_sweep) if not na(ls_pl_val)     float swing_rvol = calc_rvol()[ls_length]     float raw_v      = volume[ls_length]     if swing_rvol >= ls_threshold or (high[ls_length] - low[ls_length]) > atr_val         bool found_eql = false         if array.size(arr_lows) > 0             for i = 0 to array.size(arr_lows) - 1                 liq_point prev_p = array.get(arr_lows, i)                 if math.abs(ls_pl_val - prev_p.price) < (atr_val * ls_eq_tol) and not prev_p.is_broken                     found_eql := true                     line.set_color(prev_p.ln, ls_col_eq)                     line.set_style(prev_p.ln, line.style_dashed)                     label.set_text(prev_p.lbl, "EQL (" + format_vol_liq(prev_p.raw_vol) + ")")                     label.set_textcolor(prev_p.lbl, ls_col_eq)                     prev_p.is_eq := true                     break         color  fin_col  = found_eql ? ls_col_eq : ls_col_l         string base_txt = found_eql ? "EQL" : "SSL"         string full_txt = base_txt + " (" + format_vol_liq(raw_v) + ")"         line  new_ln  = line.new(bar_index[ls_length], ls_pl_val, bar_index, ls_pl_val, color=fin_col, style=found_eql ? line.style_dashed : line.style_solid, width=1)         label new_lbl = label.new(bar_index, ls_pl_val, full_txt, color=color.new(color.white, 100), style=label.style_none, size=size.tiny, textcolor=col_text, yloc=yloc.price)         array.unshift(arr_lows, liq_point.new(ls_pl_val, swing_rvol, raw_v, false, na, new_ln, new_lbl, found_eql, na, false))         if array.size(arr_lows) > ls_max_back             liq_point old = array.pop(arr_lows)             line.delete(old.ln),  label.delete(old.lbl)             if not na(old.lbl_sweep)                 label.delete(old.lbl_sweep) //============================================================================= // 9. INTERACTION LOGIC — FIXED FAKEOUT DETECTION //============================================================================= float atr = atr_val // --- Highs --- if array.size(arr_highs) > 0     for i = array.size(arr_highs) - 1 to 0         liq_point p = array.get(arr_highs, i)         if not p.is_broken             line.set_x2(p.ln, bar_index)             label.set_x(p.lbl, bar_index)             if not na(p.lbl_sweep)                 label.set_x(p.lbl_sweep, bar_index)             if high > p.price and not p.is_swept                 p.is_swept := true                 line.set_color(p.ln, color.purple)                 label lbl_sw = label.new(bar_index, p.price + atr * 0.3, "SWEEP", color=color.new(color.white, 100), textcolor=color.purple, style=label.style_none, size=size.tiny, yloc=yloc.price)                 p.lbl_sweep := lbl_sw             if close > p.price                 p.is_broken := true                 p.break_idx := bar_index                 // Garis disembunyikan segera saat diambil                 line.set_color(p.ln, na)                 label.set_textcolor(p.lbl, na)                 if not na(p.lbl_sweep)                     label.delete(p.lbl_sweep)                     p.lbl_sweep := na         else             if (bar_index - p.break_idx) <= ls_conf_bars and close < p.price                 // Kembalikan objek jika hanya fakeout                 p.is_broken := false                 p.break_idx := na                 p.is_swept  := false                 color  restore_col = p.is_eq ? ls_col_eq : ls_col_h                 string restore_txt = p.is_eq ? "EQH (" + format_vol_liq(p.raw_vol) + ")" : "BSL (" + format_vol_liq(p.raw_vol) + ")"                 line.set_color(p.ln, restore_col)                 line.set_style(p.ln, p.is_eq ? line.style_dashed : line.style_solid)                 label.set_text(p.lbl, restore_txt)                 label.set_textcolor(p.lbl, col_text)             else if (bar_index - p.break_idx) > ls_conf_bars                 // Hapus sepenuhnya setelah valid terambil                 line.delete(p.ln)                 label.delete(p.lbl)                 array.remove(arr_highs, i) // --- Lows --- if array.size(arr_lows) > 0     for i = array.size(arr_lows) - 1 to 0         liq_point p = array.get(arr_lows, i)         if not p.is_broken             line.set_x2(p.ln, bar_index)             label.set_x(p.lbl, bar_index)             if not na(p.lbl_sweep)                 label.set_x(p.lbl_sweep, bar_index)             if low < p.price and not p.is_swept                 p.is_swept := true                 line.set_color(p.ln, color.purple)                 label lbl_sw = label.new(bar_index, p.price - atr * 0.3, "SWEEP", color=color.new(color.white, 100), textcolor=color.purple, style=label.style_none, size=size.tiny, yloc=yloc.price)                 p.lbl_sweep := lbl_sw             if close < p.price                 p.is_broken := true                 p.break_idx := bar_index                 // Garis disembunyikan segera saat diambil                 line.set_color(p.ln, na)                 label.set_textcolor(p.lbl, na)                 if not na(p.lbl_sweep)                     label.delete(p.lbl_sweep)                     p.lbl_sweep := na         else             if (bar_index - p.break_idx) <= ls_conf_bars and close > p.price                 // Kembalikan objek jika hanya fakeout                 p.is_broken := false                 p.break_idx := na                 p.is_swept  := false                 color  restore_col = p.is_eq ? ls_col_eq : ls_col_l                 string restore_txt = p.is_eq ? "EQL (" + format_vol_liq(p.raw_vol) + ")" : "SSL (" + format_vol_liq(p.raw_vol) + ")"                 line.set_color(p.ln, restore_col)                 line.set_style(p.ln, p.is_eq ? line.style_dashed : line.style_solid)                 label.set_text(p.lbl, restore_txt)                 label.set_textcolor(p.lbl, col_text)             else if (bar_index - p.break_idx) > ls_conf_bars                 // Hapus sepenuhnya setelah valid terambil                 line.delete(p.ln)                 label.delete(p.lbl)                 array.remove(arr_lows, i) //============================================================================= // 10. CLEANUP (OB boxes) //============================================================================= if array.size(ob_boxes_array) > 0     for i = array.size(ob_boxes_array) - 1 to 0         box.delete(array.get(ob_boxes_array, i))     array.clear(ob_boxes_array) if showBull > 0 and barstate.islast     for i = 0 to math.min(showBull - 1, bullish_ob.size() - 1)         bullish_ob.get(i).display(bullCss, bullBreakCss, showObStr) if showBear > 0 and barstate.islast     for i = 0 to math.min(showBear - 1, bearish_ob.size() - 1)         bearish_ob.get(i).display(bearCss, bearBreakCss, showObStr) //============================================================================= // 11. LINEAR REGRESSION CHANNEL //============================================================================= var float[] fibo_ratios = array.from(0.236, 0.382, 0.618, 0.786) var color[] lr_colors   = array.new<color>(2) if barstate.isfirst     array.set(lr_colors, 0, lr_dncol)     array.set(lr_colors, 1, lr_upcol) get_channel(src, len) =>     float y2    = ta.linreg(src, len, 0)     float y1    = ta.linreg(src, len, len - 1)     float slope = len > 1 ? (y2 - y1) / (len - 1) : 0.0     float dev   = 0.0     for i = 0 to len - 1         float expected = y2 - slope * i         dev := dev + math.pow(src[i] - expected, 2)     dev := math.sqrt(dev / len)     [y1, y2, dev, slope] if show_lr     [y1_, y2_, dev, slope] = get_channel(lr_src, lr_len)     bool below_channel = close < y2_ - dev * lr_dev     bool above_channel = close > y2_ + dev * lr_dev     int  outofchannel  = (slope > 0 and below_channel) ? 0 : (slope < 0 and above_channel) ? 2 : -1     var line[] reglines  = array.new_line(3)     var line[] fibolines = array.new_line(4)     color cur_col = array.get(lr_colors, math.round(math.max(math.sign(slope), 0)))     for x = 0 to 2         if not lr_showbrk or outofchannel != x or nz(outofchannel[1], -1) != -1             line.delete(array.get(reglines, x))         else             line.set_color(array.get(reglines, x), lr_brkcol)             line.set_width(array.get(reglines, x), 1)             line.set_style(array.get(reglines, x), line.style_dotted)             line.set_extend(array.get(reglines, x), extend.none)         float offset = dev * lr_dev * (x - 1)         array.set(reglines, x,              line.new(x1=bar_index - (lr_len - 1), y1=y1_ + offset, x2=bar_index, y2=y2_ + offset,                       color=cur_col, style=x % 2 == 1 ? line.style_solid : line.style_dashed, width=1,                       extend=lr_extend ? extend.right : extend.none))     if lr_fibo         for x = 0 to 3             line.delete(array.get(fibolines, x))             float fibo_off = -dev * lr_dev + dev * lr_dev * 2 * array.get(fibo_ratios, x)             array.set(fibolines, x,                  line.new(x1=bar_index - (lr_len - 1), y1=y1_ + fibo_off, x2=bar_index, y2=y2_ + fibo_off,                           color=color.new(cur_col, 50), style=line.style_dotted, width=1,                           extend=lr_extend ? extend.right : extend.none))     var label sidelab = label.new(bar_index - (lr_len - 1), y1_, "S", size=size.normal, style=label.style_none)     string txt        = slope > 0 ? (slope > slope[1] ? "⇑" : "⇗") : slope < 0 ? (slope < slope[1] ? "⇓" : "⇘") : "⇒"     color  cur_col_lbl = slope > 0 ? lr_upcol : slope < 0 ? lr_dncol : lr_brkcol     label.set_text(sidelab, txt)     label.set_x(sidelab, bar_index - (lr_len - 1))     label.set_y(sidelab, slope > 0 ? y1_ - dev * lr_dev : slope < 0 ? y1_ + dev * lr_dev : y1_)     label.set_textcolor(sidelab, cur_col_lbl) simpan saja.
Percakapan dengan Gemini
dimana bisa mencoba hosting gratis project ini unutk kebutuhkan portofolio nanti

Menghosting aplikasi modern dengan stack Laravel 11, Inertia React, Tailwind, dan MySQL secara gratis untuk portofolio memang membutuhkan sedikit strategi. Karena aplikasi Anda membutuhkan backend PHP 8.3, proses build Node.js (Vite), dan layanan queue worker di background, tidak semua hosting gratis biasa bisa menanganinya dengan sempurna.

Berikut adalah rekomendasi platform hosting gratis terbaik yang bisa Anda manfaatkan untuk proyek boilerplate ini, diurutkan berdasarkan fleksibilitas dan kecocokannya.

1. Oracle Cloud (Always Free Tier) - Sangat Direkomendasikan
Oracle Cloud menawarkan tier gratis seumur hidup yang paling tidak masuk akal (dalam konotasi positif) di pasaran saat ini. Anda akan mendapatkan Virtual Private Server (VPS) utuh.

Spesifikasi Gratis: 4 ARM Ampere A1 Compute instances dengan RAM hingga 24 GB, dan Storage 200 GB.

Kelebihan: Anda punya akses root/SSH penuh. Anda bisa menginstal PHP 8.3, MySQL 8, Node.js 20, dan menjalankan php artisan queue:work atau Supervisor di background tanpa batasan.

Kekurangan: Membutuhkan pengetahuan dasar Linux (Ubuntu) untuk setup server (Nginx/Apache, sertifikat SSL) dari nol. Wajib memasukkan kartu kredit/debit untuk verifikasi (meskipun tidak akan ditagih).

2. Render (PaaS) + External Database (Misal: Aiven atau TiDB)
Render adalah Platform as a Service (PaaS) yang sangat populer menggantikan Heroku. Render akan otomatis menarik kode Anda dari GitHub dan melakukan proses build.

Cara Kerja: Anda menggunakan layanan Web Service gratis dari Render untuk menjalankan PHP/Laravel. Karena Render tidak menyediakan MySQL gratis yang permanen, Anda harus mengkoneksikan database dari layanan pihak ketiga yang menyediakan MySQL gratis (seperti Aiven, TiDB Serverless, atau db4free).

Kelebihan: Deploy sangat mudah via GitHub (CI/CD otomatis). Tidak perlu pusing mengatur sistem operasi server.

Kekurangan: Layanan gratis Render akan "tertidur" (spin down) jika tidak ada trafik selama 15 menit, sehingga butuh waktu sekitar 30-50 detik untuk bangun saat diakses pertama kali. Queue worker untuk memproses ekspor/email mungkin tidak bisa berjalan ideal di versi gratis.

3. InfinityFree atau CloudAccess (Shared Hosting Gratis)
Jika Anda tidak memiliki kartu kredit untuk verifikasi atau tidak ingin repot dengan server VPS, Shared Hosting gratis adalah alternatif terakhir.

Cara Kerja: Menyediakan environment PHP dan MySQL gratis melalui kontrol panel (seperti cPanel/VistaPanel).

Kelebihan: Benar-benar gratis, langsung jadi, dan sangat ramah untuk pemula.

Kekurangan: Tidak ada akses terminal (SSH). Anda tidak bisa menjalankan composer install atau npm run dev di server.

Catatan Penting untuk Shared Hosting: Anda harus melakukan build di komputer lokal Anda terlebih dahulu (npm run build), lalu mengunggah seluruh folder (termasuk folder vendor dan public/build) secara manual via FTP. Anda juga tidak bisa menjalankan worker background (php artisan queue:work), sehingga di file .env, QUEUE_CONNECTION harus diubah kembali menjadi sync.

💡 Tips Deployment Portofolio
Berdasarkan dokumen panduan boilerplate Anda, perhatikan hal-hal berikut sebelum mengunggah proyek ke server produksi:

Build Frontend: Selalu jalankan npm run build (bukan npm run dev) agar Vite mengompilasi aset React/Tailwind Anda menjadi file statis yang ringan.

Symlink Storage: Jangan lupa untuk menjalankan php artisan storage:link (atau atur manual di cPanel jika memakai shared hosting) agar file unggahan Anda bisa terbaca publik.

Matikan Debug: Pastikan APP_ENV=production dan APP_DEBUG=false di file .env server Anda agar informasi sensitif tidak bocor saat terjadi error.

Apakah Anda lebih tertarik menggunakan VPS (seperti Oracle Cloud) agar bebas mengatur environment sendiri, atau lebih suka model PaaS (seperti Render) yang lebih otomatis meskipun ada batasan performa?

S C:\Users\arbil\Documents\0 project\0 boilerplate\laravel> php artisan migrate    



   Illuminate\Database\QueryException 



  SQLSTATE[HY000]: General error: 1273 Unknown collation: 'utf8mb4_0900_ai_ci' (Connection: mysql, SQL: select exists (select 1 from information_schema.tables where table_schema = 'boilerplate' and table_name = 'migrations' and table_type in ('BASE TABLE', 'SYSTEM VERSIONED')) as `exists`)



  at vendor\laravel\framework\src\Illuminate\Database\Connection.php:825

    821▕                     $this->getName(), $query, $this->prepareBindings($bindings), $e

    822▕                 );

    823▕             }

    824▕ 

  ➜ 825▕             throw new QueryException(

    826▕                 $this->getName(), $query, $this->prepareBindings($bindings), $e

    827▕             );

    828▕         }

    829▕     }



  1   vendor\laravel\framework\src\Illuminate\Database\Connectors\MySqlConnector.php:121

      PDOException::("SQLSTATE[HY000]: General error: 1273 Unknown collation: 'utf8mb4_0900_ai_ci'")



  2   vendor\laravel\framework\src\Illuminate\Database\Connectors\MySqlConnector.php:121

      PDO::exec("SET NAMES 'utf8mb4' COLLATE 'utf8mb4_0900_ai_ci', SESSION sql_mode='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';")



PS C:\Users\arbil\Documents\0 project\0 boilerplate\laravel> 

Error ini sangat umum terjadi di Laravel 11. Penyebab utamanya adalah Laravel 11 secara default dikonfigurasi untuk MySQL versi 8.0 ke atas, yang menggunakan collation utf8mb4_0900_ai_ci.

Namun, database di komputer lokal Anda (kemungkinan besar menggunakan XAMPP, Laragon, atau MySQL versi 5.7) menggunakan MariaDB atau versi MySQL lama yang tidak mengenali collation tersebut.

Berikut adalah cara tercepat dan paling aman untuk memperbaikinya:

Solusi: Ubah Collation di file .env
Anda hanya perlu memberi tahu Laravel untuk menggunakan standar collation lama yang didukung oleh semua jenis database (termasuk MariaDB bawaan XAMPP).

Langkah 1: Buka file .env di folder root proyek Laravel Anda.

Langkah 2: Cari bagian pengaturan database (biasanya diawali dengan DB_). Tambahkan baris DB_COLLATION=utf8mb4_unicode_ci di bawah DB_CHARSET (atau di bawah DB_PASSWORD jika DB_CHARSET tidak ada).

Bentuknya akan menjadi seperti ini:

Cuplikan kode
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=boilerplate
DB_USERNAME=root
DB_PASSWORD=
DB_COLLATION=utf8mb4_unicode_ci 
(Pastikan Anda mengetik utf8mb4_unicode_ci dengan benar tanpa spasi ekstra di belakangnya)

Langkah 3: Bersihkan cache konfigurasi Laravel agar perubahan di file .env terbaca. Jalankan perintah ini di terminal:

Bash
php artisan config:clear
Langkah 4: Jalankan ulang perintah migrasi:

Bash
php artisan migrate
Sekarang migrasi Anda seharusnya bisa berjalan dengan lancar dan tabel-tabel akan berhasil dibuat di database boilerplate.

Catatan Tambahan: Jika Anda menggunakan XAMPP terbaru, Anda juga punya opsi alternatif mengubah DB_CONNECTION=mysql menjadi DB_CONNECTION=mariadb di file .env (fitur baru di Laravel 11), tetapi menambahkan DB_COLLATION seperti cara di atas adalah solusi yang paling ant-gagal untuk berbagai versi localhost.

konversikan menjadi .md lengkap.

Langkah 2 — Starter Kit Breeze (React + Inertia + Tailwind) [cite: 1]
Breeze menyiapkan autentikasi dasar sekaligus mengonfigurasi React, Inertia.js, dan Tailwind CSS dalam satu perintah. [cite: 1]

Bash
composer require laravel/breeze --dev
php artisan breeze:install react
Langkah 3 — Package Wajib Standar Enterprise [cite: 1]
Package	Fungsi
spatie/laravel-permission [cite: 1]	Role & permission (mis. admin, customer) [cite: 1]
owen-it/laravel-auditing [cite: 1]	Audit trail / log perubahan data [cite: 1]
maatwebsite/excel [cite: 1]	Export & import Excel [cite: 1]
Bash
composer require spatie/laravel-permission
composer require owen-it/laravel-auditing
composer require maatwebsite/excel
Langkah 4 — Konfigurasi File .env [cite: 1]
Sesuaikan koneksi database, lalu ubah driver queue ke database supaya proses berat (export/import, kirim email) berjalan di background. [cite: 1]

Cuplikan kode
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_nama_project
DB_USERNAME=root
DB_PASSWORD=
 
QUEUE_CONNECTION=database
Langkah 5 — Publikasi Konfigurasi & Migrasi Database [cite: 1]
Bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
php artisan vendor:publish --provider="OwenIt\Auditing\AuditingServiceProvider"
php artisan migrate
Catatan: Di Laravel 11, tabel queue jobs umumnya sudah tersedia di migrasi default — tidak perlu publish tambahan. [cite: 1]

Langkah 6 — Symlink Storage & Setup Frontend [cite: 1]
Menghubungkan folder storage agar file upload (gambar produk, dokumen) bisa diakses browser, lalu memasang dependency frontend. [cite: 1]

Bash
php artisan storage:link
npm install
npm install react-select
3. Menjalankan Aplikasi (Development) [cite: 1]
Buka 3 terminal terpisah di root proyek — ketiganya harus jalan bersamaan selama development. [cite: 1]

Terminal	Perintah	Fungsi
1 [cite: 1]	php artisan serve [cite: 1]	Server backend Laravel. Akses: http://localhost:8000 [cite: 1]
2 [cite: 1]	npm run dev [cite: 1]	Build & hot-reload aset frontend (React/Tailwind) via Vite [cite: 1]
3 [cite: 1]	php artisan queue:work [cite: 1]	Worker background: export/import Excel, kirim email, dll [cite: 1]
4. Struktur Direktori Standar Proyek [cite: 1]
Ini adalah struktur baku yang wajib diikuti. [cite: 1] Tiga area utama dipisah jelas — Public (halaman umum/company profile & katalog), Customer (area setelah login), Admin (dashboard pengelolaan) — plus Api untuk kebutuhan integrasi eksternal. [cite: 1]

Plaintext
nama-project/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── Admin/              -> Dashboard admin (CRUD produk, user, laporan)
│   │   │   │   ├── DashboardController.php
│   │   │   │   ├── ProductController.php
│   │   │   │   ├── CategoryController.php
│   │   │   │   └── UserController.php
│   │   │   ├── Customer/           -> Area akun customer (wajib login)
│   │   │   │   ├── ProfileController.php
│   │   │   │   └── OrderController.php
│   │   │   ├── Public/             -> Halaman umum (tanpa login)
│   │   │   │   ├── HomeController.php
│   │   │   │   ├── CatalogController.php
│   │   │   │   └── ContactController.php
│   │   │   ├── Api/V1/             -> Controller khusus API (return JSON)
│   │   │   │   ├── ProductApiController.php
│   │   │   │   └── AuthApiController.php
│   │   │   └── Auth/               -> Bawaan Breeze (login, register, dll)
│   │   ├── Middleware/
│   │   │   └── IsAdmin.php         -> Cek role sebelum masuk area admin
│   │   ├── Requests/               -> Form validation, dikelompokkan per area
│   │   │   ├── Admin/
│   │   │   ├── Customer/
│   │   │   └── Public/
│   │   └── Resources/              -> Transformer JSON untuk API
│   │       ├── ProductResource.php
│   │       └── UserResource.php
│   └── Models/
│       ├── Product.php
│       ├── Category.php
│       ├── Order.php
│       └── User.php
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── factories/
├── resources/
│   ├── js/
│   │   ├── Pages/                  -> 1 file = 1 halaman (di-render Inertia)
│   │   │   ├── Admin/
│   │   │   │   ├── Dashboard.jsx
│   │   │   │   ├── Products/{Index,Create,Edit}.jsx
│   │   │   │   └── Users/Index.jsx
│   │   │   ├── Public/
│   │   │   │   ├── Home.jsx
│   │   │   │   ├── Catalog/{Index,Detail}.jsx
│   │   │   │   └── Contact.jsx
│   │   │   ├── Customer/
│   │   │   │   ├── Profile/Edit.jsx
│   │   │   │   └── Orders/Index.jsx
│   │   │   └── Auth/               -> Bawaan Breeze
│   │   ├── Layouts/
│   │   │   ├── AdminLayout.jsx     -> Sidebar + topbar dashboard
│   │   │   ├── PublicLayout.jsx    -> Navbar + footer situs umum
│   │   │   └── CustomerLayout.jsx  -> Layout area akun customer
│   │   ├── Components/
│   │   │   ├── Admin/
│   │   │   ├── Public/
│   │   │   └── Shared/             -> Button, Input, Modal (reusable lintas area)
│   │   └── app.jsx
│   └── css/app.css
├── routes/
│   ├── web.php                     -> Semua route Inertia (public+customer+admin)
│   ├── api.php                     -> Semua route API (mobile app/integrasi luar)
│   └── auth.php                    -> Bawaan Breeze
├── public/
│   └── storage -> symlink ke storage/app/public
└── .env
Aturan Penempatan File [cite: 1]
Folder / File	Fungsi
Http/Controllers/Admin [cite: 1]	Semua controller fitur dashboard: kelola produk, kategori, user, laporan. [cite: 1]
Http/Controllers/Customer [cite: 1]	Controller area akun setelah login: profil, riwayat pesanan. [cite: 1]
Http/Controllers/Public [cite: 1]	Controller halaman tanpa login: beranda, katalog produk, kontak. [cite: 1]
Http/Controllers/Api/V1 [cite: 1]	Controller API murni (JSON) untuk mobile app / pihak ketiga. [cite: 1]
resources/js/Pages/Admin [cite: 1]	Halaman React dashboard admin. [cite: 1]
resources/js/Pages/Public [cite: 1]	Halaman React untuk company profile & katalog publik. [cite: 1]
resources/js/Pages/Customer [cite: 1]	Halaman React area akun customer. [cite: 1]
resources/js/Layouts [cite: 1]	Kerangka tampilan (sidebar/navbar/footer) per area — dipakai berulang. [cite: 1]
resources/js/Components/Shared [cite: 1]	Komponen kecil reusable lintas area (tombol, input, modal). [cite: 1]
Catatan: Satu Controller hanya menangani satu area (Admin/Customer/Public/Api). [cite: 1] Jangan campur logic admin dan public dalam satu Controller — memudahkan tracking hak akses dan maintenance. [cite: 1]

5. Konvensi Routing [cite: 1]
Semua route halaman (Inertia) tetap satu file routes/web.php, dikelompokkan per area pakai prefix + name + middleware. [cite: 1] Route API murni dipisah ke routes/api.php (lihat Bab 6). [cite: 1]

PHP
// routes/web.php
 
// --- Public (tanpa login) ---
Route::get('/', [HomeController::class, 'index'])->name('home');
Route::get('/katalog', [CatalogController::class, 'index'])->name('catalog');
Route::get('/katalog/{slug}', [CatalogController::class, 'show'])->name('catalog.show');
Route::get('/kontak', [ContactController::class, 'index'])->name('contact');
 
// --- Customer (wajib login) ---
Route::middleware(['auth', 'verified'])->prefix('akun')->name('customer.')->group(function () {
    Route::get('/profil', [ProfileController::class, 'edit'])->name('profile.edit');
    Route::get('/pesanan', [OrderController::class, 'index'])->name('orders.index');
});
 
// --- Admin (wajib login + role admin) ---
Route::middleware(['auth', 'is_admin'])->prefix('admin')->name('admin.')->group(function () {
    Route::get('/dashboard', [DashboardController::class, 'index'])->name('dashboard');
    Route::resource('products', ProductController::class);
    Route::resource('categories', CategoryController::class);
});
Middleware Role Admin (Laravel 11) [cite: 1]
Laravel 11 mendaftarkan middleware alias lewat bootstrap/app.php, bukan lagi Kernel.php. [cite: 1]

Bash
php artisan make:middleware IsAdmin
PHP
// bootstrap/app.php
->withMiddleware(function (Middleware $middleware) {$middleware->alias([
        'is_admin' => \App\Http\Middleware\IsAdmin::class,
    ]);
})
PHP
// Contoh assign role via Tinker / seeder (Spatie Permission)
$user->assignRole('admin');
6. Panduan Integrasi API [cite: 1]
6.1 Kapan Perlu API Terpisah? [cite: 1]
Halaman yang di-render Inertia (Pages/*) sudah otomatis menerima data dari Controller lewat Inertia::render() — tidak perlu fetch API tambahan untuk load halaman. [cite: 1] routes/api.php baru dibutuhkan untuk: [cite: 1]

Aplikasi mobile (Android/iOS) yang konsumsi data dari backend yang sama. [cite: 1]

Integrasi pihak ketiga (mis. sistem gudang, marketplace). [cite: 1]

Interaksi partial di halaman tanpa reload penuh — mis. live search, badge keranjang, notifikasi. [cite: 1]

6.2 Setup Sanctum (Autentikasi Token API) [cite: 1]
Bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
6.3 Struktur routes/api.php [cite: 1]
Gunakan versioning (v1) sejak awal supaya perubahan struktur di masa depan tidak merusak konsumen API yang sudah berjalan. [cite: 1]

PHP
// routes/api.php
use App\Http\Controllers\Api\V1\ProductApiController;
use App\Http\Controllers\Api\V1\AuthApiController;
 
Route::prefix('v1')->group(function () {
    Route::post('/login', [AuthApiController::class, 'login']);
 
    Route::middleware('auth:sanctum')->group(function () {
        Route::get('/profile', [AuthApiController::class, 'profile']);
        Route::get('/products', [ProductApiController::class, 'index']);
        Route::get('/products/{id}', [ProductApiController::class, 'show']);
    });
});
6.4 Controller API + API Resource [cite: 1]
Controller API hanya mengembalikan JSON — gunakan Resource agar format response konsisten dan tidak membocorkan kolom sensitif. [cite: 1]

Bash
php artisan make:resource ProductResource
PHP
// app/Http/Resources/ProductResource.php
public function toArray($request)
{
    return [
        'id'    => $this->id,
        'name'  => $this->name,
        'price' => $this->price,
        'image' => asset('storage/' . $this->image),
    ];
}
PHP
// app/Http/Controllers/Api/V1/ProductApiController.php
public function index()
{
    $products = Product::latest()->paginate(12);
    return ProductResource::collection($products);
}
6.5 Konsumsi API dari Frontend (React/axios) [cite: 1]
Dipakai untuk kasus di luar Inertia page-load biasa, misalnya live search di halaman katalog. [cite: 1]

JavaScript
// resources/js/Pages/Public/Catalog/Index.jsx
import axios from 'axios';
 
async function searchProducts(keyword) {
  const res = await axios.get('/api/v1/products', { params: { q: keyword } });
  return res.data.data; // hasil sudah lewat ProductResource
}
Catatan: axios sudah otomatis dikonfigurasi Breeze (baseURL & header) — tidak perlu setup ulang. [cite: 1]

6.6 CORS (Jika API Diakses dari Domain/App Lain) [cite: 1]
Jika API dikonsumsi dari luar (aplikasi mobile terpisah, domain frontend berbeda), atur config/cors.php: [cite: 1]

PHP
// config/cors.php
'paths' => ['api/*', 'sanctum/csrf-cookie'],
'allowed_origins' => ['[https://app-mobile-domain.com](https://app-mobile-domain.com)'],
'supports_credentials' => true,
7. Checklist Sebelum Mulai Development [cite: 1]
php artisan serve, npm run dev, dan php artisan queue:work jalan tanpa error di 3 terminal. [cite: 1]

Migrasi database sukses (php artisan migrate) — tabel Spatie & Auditing sudah ada. [cite: 1]

php artisan storage:link sudah dijalankan (upload gambar bisa diakses via /storage/...). [cite: 1]

Controller baru ditempatkan sesuai area: Admin / Customer / Public / Api\V1 — tidak dicampur. [cite: 1]

Halaman React baru ditaruh di resources/js/Pages/<Area>/ sesuai controller yang memanggilnya. [cite: 1]

Route baru didaftarkan dengan prefix + name + middleware yang sesuai area. [cite: 1]

Role user (admin/customer) sudah di-assign lewat Spatie sebelum testing akses dashboard. [cite: 1]

Struktur di atas adalah kerangka baku. [cite: 1] Di luar itu — fitur, package tambahan, styling, dsb. — bebas dikembangkan mengikuti kebutuhan masing-masing proyek. [cite: 1]
"""

filename = "Panduan-Internal-Proyek-Boilerplate.md"
with open(filename, "w", encoding="utf-8") as f:
f.write(markdown_content)

print(f"File successfully created: {filename}")


```text?code_stdout&code_event_index=1
File successfully created: Panduan-Internal-Proyek-Boilerplate.md

Your MD file is ready
Ikon MD
Panduan-Internal-Proyek-Boilerplate
 MD 
Buka

Dokumen panduan proyek Anda telah berhasil dikonversi dan diformat secara rapi ke dalam bentuk file Markdown (.md). File tersebut siap untuk Anda gunakan sebagai dokumentasi pada repository (seperti README.md) maupun untuk dibagikan kepada tim pengembang.




Gemini adalah AI dan dapat melakukan kesalahan.

# PANDUAN INTERNAL PROYEK [cite: 1]
## Setup, Instalasi & Struktur Direktori Boilerplate [cite: 1]
**Company Profile & E-Commerce — Laravel 11 + Inertia React + Tailwind** [cite: 1]
*Fixed-version strategy — dikunci agar bebas dependency hell* [cite: 1]

Dokumen ini adalah panduan baku (standard) yang wajib diikuti setiap kali memulai proyek baru dari boilerplate ini. [cite: 1] Tujuannya: junior dev bisa langsung jalan tanpa nebak-nebak — mulai dari instalasi, penempatan file di folder yang benar, sampai cara menyambungkan API. [cite: 1] Struktur di luar panduan ini (fitur, tambahan modul, dsb.) bebas dikembangkan mengikuti kebutuhan masing-masing proyek. [cite: 1]

## Daftar Isi [cite: 1]
1. Prasyarat Sistem [cite: 1]
2. Langkah Instalasi (Terminal) [cite: 1]
3. Menjalankan Aplikasi (Development) [cite: 1]
4. Struktur Direktori Standar Proyek [cite: 1]
5. Konvensi Routing [cite: 1]
6. Panduan Integrasi API [cite: 1]
7. Checklist Sebelum Mulai Development [cite: 1]

## 1. Prasyarat Sistem [cite: 1]
Pastikan environment berikut sudah terpasang sebelum instalasi. [cite: 1] Versi dikunci agar seluruh tim memakai konfigurasi yang identik. [cite: 1]

| Komponen | Versi Minimum | Cek dengan |
|---|---|---|
| PHP | 8.3 atau lebih baru [cite: 1] | `php -v` [cite: 1] |
| Composer | 2.x [cite: 1] | `composer -V` [cite: 1] |
| Node.js & npm | Node.js 20 (LTS) atau lebih baru [cite: 1] | `node -v && npm -v` [cite: 1] |
| Database | MySQL 8.x atau MariaDB setara [cite: 1] | `mysql --version` [cite: 1] |

## 2. Langkah Instalasi (Terminal) [cite: 1]
Jalankan berurutan dari atas ke bawah. [cite: 1] Semua perintah dieksekusi dari root folder proyek kecuali disebutkan lain. [cite: 1]

### Langkah 1 — Membuat Proyek Laravel 11 [cite: 1]
```bash
composer create-project laravel/laravel:^11.0 nama-project
cd nama-project
```

### Langkah 2 — Starter Kit Breeze (React + Inertia + Tailwind) [cite: 1]
Breeze menyiapkan autentikasi dasar sekaligus mengonfigurasi React, Inertia.js, dan Tailwind CSS dalam satu perintah. [cite: 1]
```bash
composer require laravel/breeze --dev
php artisan breeze:install react
```

### Langkah 3 — Package Wajib Standar Enterprise [cite: 1]
| Package | Fungsi |
|---|---|
| `spatie/laravel-permission` [cite: 1] | Role & permission (mis. admin, customer) [cite: 1] |
| `owen-it/laravel-auditing` [cite: 1] | Audit trail / log perubahan data [cite: 1] |
| `maatwebsite/excel` [cite: 1] | Export & import Excel [cite: 1] |

```bash
composer require spatie/laravel-permission
composer require owen-it/laravel-auditing
composer require maatwebsite/excel
```

### Langkah 4 — Konfigurasi File .env [cite: 1]
Sesuaikan koneksi database, lalu ubah driver queue ke database supaya proses berat (export/import, kirim email) berjalan di background. [cite: 1]
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_nama_project
DB_USERNAME=root
DB_PASSWORD=
 
QUEUE_CONNECTION=database
```

### Langkah 5 — Publikasi Konfigurasi & Migrasi Database [cite: 1]
```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
php artisan vendor:publish --provider="OwenIt\Auditing\AuditingServiceProvider"
php artisan migrate
```
Catatan: Di Laravel 11, tabel queue jobs umumnya sudah tersedia di migrasi default — tidak perlu publish tambahan. [cite: 1]

### Langkah 6 — Symlink Storage & Setup Frontend [cite: 1]
Menghubungkan folder storage agar file upload (gambar produk, dokumen) bisa diakses browser, lalu memasang dependency frontend. [cite: 1]
```bash
php artisan storage:link
npm install
npm install react-select
```

## 3. Menjalankan Aplikasi (Development) [cite: 1]
Buka 3 terminal terpisah di root proyek — ketiganya harus jalan bersamaan selama development. [cite: 1]

| Terminal | Perintah | Fungsi |
|---|---|---|
| 1 [cite: 1] | `php artisan serve` [cite: 1] | Server backend Laravel. Akses: `http://localhost:8000` [cite: 1] |
| 2 [cite: 1] | `npm run dev` [cite: 1] | Build & hot-reload aset frontend (React/Tailwind) via Vite [cite: 1] |
| 3 [cite: 1] | `php artisan queue:work` [cite: 1] | Worker background: export/import Excel, kirim email, dll [cite: 1] |

## 4. Struktur Direktori Standar Proyek [cite: 1]
Ini adalah struktur baku yang wajib diikuti. [cite: 1] Tiga area utama dipisah jelas — Public (halaman umum/company profile & katalog), Customer (area setelah login), Admin (dashboard pengelolaan) — plus Api untuk kebutuhan integrasi eksternal. [cite: 1]

```text
nama-project/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── Admin/              -> Dashboard admin (CRUD produk, user, laporan)
│   │   │   │   ├── DashboardController.php
│   │   │   │   ├── ProductController.php
│   │   │   │   ├── CategoryController.php
│   │   │   │   └── UserController.php
│   │   │   ├── Customer/           -> Area akun customer (wajib login)
│   │   │   │   ├── ProfileController.php
│   │   │   │   └── OrderController.php
│   │   │   ├── Public/             -> Halaman umum (tanpa login)
│   │   │   │   ├── HomeController.php
│   │   │   │   ├── CatalogController.php
│   │   │   │   └── ContactController.php
│   │   │   ├── Api/V1/             -> Controller khusus API (return JSON)
│   │   │   │   ├── ProductApiController.php
│   │   │   │   └── AuthApiController.php
│   │   │   └── Auth/               -> Bawaan Breeze (login, register, dll)
│   │   ├── Middleware/
│   │   │   └── IsAdmin.php         -> Cek role sebelum masuk area admin
│   │   ├── Requests/               -> Form validation, dikelompokkan per area
│   │   │   ├── Admin/
│   │   │   ├── Customer/
│   │   │   └── Public/
│   │   └── Resources/              -> Transformer JSON untuk API
│   │       ├── ProductResource.php
│   │       └── UserResource.php
│   └── Models/
│       ├── Product.php
│       ├── Category.php
│       ├── Order.php
│       └── User.php
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── factories/
├── resources/
│   ├── js/
│   │   ├── Pages/                  -> 1 file = 1 halaman (di-render Inertia)
│   │   │   ├── Admin/
│   │   │   │   ├── Dashboard.jsx
│   │   │   │   ├── Products/{Index,Create,Edit}.jsx
│   │   │   │   └── Users/Index.jsx
│   │   │   ├── Public/
│   │   │   │   ├── Home.jsx
│   │   │   │   ├── Catalog/{Index,Detail}.jsx
│   │   │   │   └── Contact.jsx
│   │   │   ├── Customer/
│   │   │   │   ├── Profile/Edit.jsx
│   │   │   │   └── Orders/Index.jsx
│   │   │   └── Auth/               -> Bawaan Breeze
│   │   ├── Layouts/
│   │   │   ├── AdminLayout.jsx     -> Sidebar + topbar dashboard
│   │   │   ├── PublicLayout.jsx    -> Navbar + footer situs umum
│   │   │   └── CustomerLayout.jsx  -> Layout area akun customer
│   │   ├── Components/
│   │   │   ├── Admin/
│   │   │   ├── Public/
│   │   │   └── Shared/             -> Button, Input, Modal (reusable lintas area)
│   │   └── app.jsx
│   └── css/app.css
├── routes/
│   ├── web.php                     -> Semua route Inertia (public+customer+admin)
│   ├── api.php                     -> Semua route API (mobile app/integrasi luar)
│   └── auth.php                    -> Bawaan Breeze
├── public/
│   └── storage -> symlink ke storage/app/public
└── .env
```

### Aturan Penempatan File [cite: 1]
| Folder / File | Fungsi |
|---|---|
| `Http/Controllers/Admin` [cite: 1] | Semua controller fitur dashboard: kelola produk, kategori, user, laporan. [cite: 1] |
| `Http/Controllers/Customer` [cite: 1] | Controller area akun setelah login: profil, riwayat pesanan. [cite: 1] |
| `Http/Controllers/Public` [cite: 1] | Controller halaman tanpa login: beranda, katalog produk, kontak. [cite: 1] |
| `Http/Controllers/Api/V1` [cite: 1] | Controller API murni (JSON) untuk mobile app / pihak ketiga. [cite: 1] |
| `resources/js/Pages/Admin` [cite: 1] | Halaman React dashboard admin. [cite: 1] |
| `resources/js/Pages/Public` [cite: 1] | Halaman React untuk company profile & katalog publik. [cite: 1] |
| `resources/js/Pages/Customer` [cite: 1] | Halaman React area akun customer. [cite: 1] |
| `resources/js/Layouts` [cite: 1] | Kerangka tampilan (sidebar/navbar/footer) per area — dipakai berulang. [cite: 1] |
| `resources/js/Components/Shared` [cite: 1] | Komponen kecil reusable lintas area (tombol, input, modal). [cite: 1] |

Catatan: Satu Controller hanya menangani satu area (Admin/Customer/Public/Api). [cite: 1] Jangan campur logic admin dan public dalam satu Controller — memudahkan tracking hak akses dan maintenance. [cite: 1]

## 5. Konvensi Routing [cite: 1]
Semua route halaman (Inertia) tetap satu file `routes/web.php`, dikelompokkan per area pakai prefix + name + middleware. [cite: 1] Route API murni dipisah ke `routes/api.php` (lihat Bab 6). [cite: 1]

```php
// routes/web.php
 
// --- Public (tanpa login) ---
Route::get('/', [HomeController::class, 'index'])->name('home');
Route::get('/katalog', [CatalogController::class, 'index'])->name('catalog');
Route::get('/katalog/{slug}', [CatalogController::class, 'show'])->name('catalog.show');
Route::get('/kontak', [ContactController::class, 'index'])->name('contact');
 
// --- Customer (wajib login) ---
Route::middleware(['auth', 'verified'])->prefix('akun')->name('customer.')->group(function () {
    Route::get('/profil', [ProfileController::class, 'edit'])->name('profile.edit');
    Route::get('/pesanan', [OrderController::class, 'index'])->name('orders.index');
});
 
// --- Admin (wajib login + role admin) ---
Route::middleware(['auth', 'is_admin'])->prefix('admin')->name('admin.')->group(function () {
    Route::get('/dashboard', [DashboardController::class, 'index'])->name('dashboard');
    Route::resource('products', ProductController::class);
    Route::resource('categories', CategoryController::class);
});
```

### Middleware Role Admin (Laravel 11) [cite: 1]
Laravel 11 mendaftarkan middleware alias lewat `bootstrap/app.php`, bukan lagi `Kernel.php`. [cite: 1]
```bash
php artisan make:middleware IsAdmin
```

```php
// bootstrap/app.php
->withMiddleware(function (Middleware $middleware) {
    $middleware->alias([
        'is_admin' => \App\Http\Middleware\IsAdmin::class,
    ]);
})
```

```php
// Contoh assign role via Tinker / seeder (Spatie Permission)
$user->assignRole('admin');
```

## 6. Panduan Integrasi API [cite: 1]
### 6.1 Kapan Perlu API Terpisah? [cite: 1]
Halaman yang di-render Inertia (`Pages/*`) sudah otomatis menerima data dari Controller lewat `Inertia::render()` — tidak perlu fetch API tambahan untuk load halaman. [cite: 1] `routes/api.php` baru dibutuhkan untuk: [cite: 1]
* Aplikasi mobile (Android/iOS) yang konsumsi data dari backend yang sama. [cite: 1]
* Integrasi pihak ketiga (mis. sistem gudang, marketplace). [cite: 1]
* Interaksi partial di halaman tanpa reload penuh — mis. live search, badge keranjang, notifikasi. [cite: 1]

### 6.2 Setup Sanctum (Autentikasi Token API) [cite: 1]
```bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
```

### 6.3 Struktur `routes/api.php` [cite: 1]
Gunakan versioning (v1) sejak awal supaya perubahan struktur di masa depan tidak merusak konsumen API yang sudah berjalan. [cite: 1]
```php
// routes/api.php
use App\Http\Controllers\Api\V1\ProductApiController;
use App\Http\Controllers\Api\V1\AuthApiController;
 
Route::prefix('v1')->group(function () {
    Route::post('/login', [AuthApiController::class, 'login']);
 
    Route::middleware('auth:sanctum')->group(function () {
        Route::get('/profile', [AuthApiController::class, 'profile']);
        Route::get('/products', [ProductApiController::class, 'index']);
        Route::get('/products/{id}', [ProductApiController::class, 'show']);
    });
});
```

### 6.4 Controller API + API Resource [cite: 1]
Controller API hanya mengembalikan JSON — gunakan Resource agar format response konsisten dan tidak membocorkan kolom sensitif. [cite: 1]
```bash
php artisan make:resource ProductResource
```

```php
// app/Http/Resources/ProductResource.php
public function toArray($request)
{
    return [
        'id'    => $this->id,
        'name'  => $this->name,
        'price' => $this->price,
        'image' => asset('storage/' . $this->image),
    ];
}
```

```php
// app/Http/Controllers/Api/V1/ProductApiController.php
public function index()
{
    $products = Product::latest()->paginate(12);
    return ProductResource::collection($products);
}
```

### 6.5 Konsumsi API dari Frontend (React/axios) [cite: 1]
Dipakai untuk kasus di luar Inertia page-load biasa, misalnya live search di halaman katalog. [cite: 1]
```jsx
// resources/js/Pages/Public/Catalog/Index.jsx
import axios from 'axios';
 
async function searchProducts(keyword) {
  const res = await axios.get('/api/v1/products', { params: { q: keyword } });
  return res.data.data; // hasil sudah lewat ProductResource
}
```
Catatan: axios sudah otomatis dikonfigurasi Breeze (baseURL & header) — tidak perlu setup ulang. [cite: 1]

### 6.6 CORS (Jika API Diakses dari Domain/App Lain) [cite: 1]
Jika API dikonsumsi dari luar (aplikasi mobile terpisah, domain frontend berbeda), atur `config/cors.php`: [cite: 1]
```php
// config/cors.php
'paths' => ['api/*', 'sanctum/csrf-cookie'],
'allowed_origins' => ['https://app-mobile-domain.com'],
'supports_credentials' => true,
```

## 7. Checklist Sebelum Mulai Development [cite: 1]
* `php artisan serve`, `npm run dev`, dan `php artisan queue:work` jalan tanpa error di 3 terminal. [cite: 1]
* Migrasi database sukses (`php artisan migrate`) — tabel Spatie & Auditing sudah ada. [cite: 1]
* `php artisan storage:link` sudah dijalankan (upload gambar bisa diakses via `/storage/...`). [cite: 1]
* Controller baru ditempatkan sesuai area: Admin / Customer / Public / `Api\V1` — tidak dicampur. [cite: 1]
* Halaman React baru ditaruh di `resources/js/Pages/<Area>/` sesuai controller yang memanggilnya. [cite: 1]
* Route baru didaftarkan dengan prefix + name + middleware yang sesuai area. [cite: 1]
* Role user (admin/customer) sudah di-assign lewat Spatie sebelum testing akses dashboard. [cite: 1]

Struktur di atas adalah kerangka baku. [cite: 1] Di luar itu — fitur, package tambahan, styling, dsb. — bebas dikembangkan mengikuti kebutuhan masing-masing proyek. [cite: 1]
Panduan-Internal-Proyek-Boilerplate.md
Menampilkan Panduan-Internal-Proyek-Boilerplate.md.
