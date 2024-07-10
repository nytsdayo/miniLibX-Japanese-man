# MiniLibX ライブラリ関数マニュアル

## MiniLibX ライブラリ関数インデックス

- [mlx_init](#mlx_init)
- [mlx_new_window](#mlx_new_window)
- [mlx_loop](#mlx_loop)
- [mlx_string_put](#mlx_string_put)
- [mlx_pixel_put](#mlx_pixel_put)
- [mlx_new_image](#mlx_new_image)
- [mlx_get_data_addr](#mlx_get_data_addr)
- [mlx_put_image_to_window](#mlx_put_image_to_window)
- [mlx_destroy_window](#mlx_destroy_window)
- [mlx_destroy_image](#mlx_destroy_image)
- [mlx_clear_window](#mlx_clear_window)
- [mlx_mouse_hook](#mlx_mouse_hook)
- [mlx_key_hook](#mlx_key_hook)
- [mlx_expose_hook](#mlx_expose_hook)
- [mlx_loop_hook](#mlx_loop_hook)
- [mlx_do_sync](#mlx_do_sync)
- [mlx_get_screen_size](#mlx_get_screen_size)
- [mlx_hook](#mlx_hook)
- [mlx_int_wait_first_expose](#mlx_int_wait_first_expose)
- [mlx_put_pixel](#mlx_put_pixel)
- [mlx_set_font](#mlx_set_font)
- [mlx_xpm_to_image](#mlx_xpm_to_image)
- [mlx_xpm_file_to_image](#mlx_xpm_file_to_image)
- [mlx_png_file_to_image](#mlx_png_file_to_image)
- [mlx_destroy_display](#mlx_destroy_display)
- [mlx_set_window_title](#mlx_set_window_title)
- [mlx_get_color_value](#mlx_get_color_value)
- [mlx_sync](#mlx_sync)
- [mlx_mouse_get_pos](#mlx_mouse_get_pos)
- [mlx_mouse_move](#mlx_mouse_move)
- [mlx_mouse_hide](#mlx_mouse_hide)
- [mlx_mouse_show](#mlx_mouse_show)
- [mlx_get_visual](#mlx_get_visual)
- [mlx_int_param_event](#mlx_int_param_event)
- [mlx_int_set_win_event_mask](#mlx_int_set_win_event_mask)
- [mlx_hook_exit](#mlx_hook_exit)

## 関数説明

### mlx_init
**ファイル**: `mlx_init.c`

 * 関数: mlx_init
 * 説明: MiniLibXの初期化を行います。この関数を呼び出すことで、描画を開始するための基本設定が整います。
 * 使用方法: void *mlx_init(void);
 * 戻り値: 成功時にはMiniLibXの識別子を返し、失敗時にはNULLを返します。
 

### mlx_new_window
**ファイル**: `mlx_new_window.c`

 * 関数: mlx_new_window
 * 説明: 新しいウィンドウを作成します。
 * 使用方法: void *mlx_new_window(void *mlx_ptr, int size_x, int size_y, char *title);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - size_x: ウィンドウの幅。
 *  - size_y: ウィンドウの高さ。
 *  - title: ウィンドウのタイトル。
 * 戻り値: 作成したウィンドウの識別子を返します。


### mlx_loop
**ファイル**: `mlx_loop.c`

 * 関数: mlx_loop
 * 説明: イベントループを開始します。この関数を呼び出すことで、プログラムはイベントを処理し続けます。
 * 使用方法: int mlx_loop(void *mlx_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 * 戻り値: 常に0を返します。


### mlx_string_put
**ファイル**: `mlx_string_put.c`

 * 関数: mlx_string_put
 * 説明: ウィンドウに文字列を描画します。
 * 使用方法: int mlx_string_put(void *mlx_ptr, void *win_ptr, int x, int y, int color, char *string);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - x: 文字列の描画開始位置のX座標。
 *  - y: 文字列の描画開始位置のY座標。
 *  - color: 文字列の色。
 *  - string: 描画する文字列。
 * 戻り値: 常に0を返します。


### mlx_pixel_put
**ファイル**: `mlx_pixel_put.c`

 * 関数: mlx_pixel_put
 * 説明: ウィンドウにピクセルを描画します。
 * 使用方法: int mlx_pixel_put(void *mlx_ptr, void *win_ptr, int x, int y, int color);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - x: ピクセルのX座標。
 *  - y: ピクセルのY座標。
 *  - color: ピクセルの色。
 * 戻り値: 常に0を返します。


### mlx_new_image
**ファイル**: `mlx_new_image.c`

 * 関数: mlx_new_image
 * 説明: 新しい画像を作成します。
 * 使用方法: void *mlx_new_image(void *mlx_ptr, int width, int height);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - width: 画像の幅。
 *  - height: 画像の高さ。
 * 戻り値: 作成した画像の識別子を返します。


### mlx_get_data_addr
**ファイル**: `mlx_get_data_addr.c`

 * 関数: mlx_get_data_addr
 * 説明: 画像データへのアクセスを取得します。
 * 使用方法: char *mlx_get_data_addr(void *img_ptr, int *bits_per_pixel, int *size_line, int *endian);
 * パラメータ:
 *  - img_ptr: mlx_new_imageで取得した画像の識別子。
 *  - bits_per_pixel: 1ピクセルあたりのビット数。
 *  - size_line: 1行あたりのバイト数。
 *  - endian: エンディアン情報。
 * 戻り値: 画像データへのポインタを返します。


### mlx_put_image_to_window
**ファイル**: `mlx_put_image_to_window.c`

 * 関数: mlx_put_image_to_window
 * 説明: ウィンドウに画像を描画します。
 * 使用方法: int mlx_put_image_to_window(void *mlx_ptr, void *win_ptr, void *img_ptr, int x, int y);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - img_ptr: 描画する画像の識別子。
 *  - x: 画像の描画開始位置のX座標。
 *  - y: 画像の描画開始位置のY座標。
 * 戻り値: 常に0を返します。


### mlx_destroy_window
**ファイル**: `mlx_destroy_window.c`

 * 関数: mlx_destroy_window
 * 説明: ウィンドウを破棄します。
 * 使用方法: int mlx_destroy_window(void *mlx_ptr, void *win_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: 破棄するウィンドウの識別子。
 * 戻り値: 常に0を返します。


### mlx_destroy_image
**ファイル**: `mlx_destroy_image.c`

 * 関数: mlx_destroy_image
 * 説明: 画像を破棄します。
 * 使用方法: int mlx_destroy_image(void *mlx_ptr, void *img_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - img_ptr: 破棄する画像の識別子。
 * 戻り値: 常に0を返します。

 ### mlx_clear_window
**ファイル**: `mlx_clear_window.c`

 * 関数: mlx_clear_window
 * 説明: ウィンドウをクリアします。
 * 使用方法: int mlx_clear_window(void *mlx_ptr, void *win_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: クリアするウィンドウの識別子。
 * 戻り値: 常に0を返します。


### mlx_mouse_hook
**ファイル**: `mlx_mouse_hook.c`

 * 関数: mlx_mouse_hook
 * 説明: マウスイベントフックを設定します。
 * 使用方法: int mlx_mouse_hook(void *win_ptr, int (*funct_ptr)(), void *param);
 * パラメータ:
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - funct_ptr: マウスイベント処理関数へのポインタ。
 *  - param: 関数に渡すパラメータ。
 * 戻り値: 常に0を返します。


### mlx_key_hook
**ファイル**: `mlx_key_hook.c`

 * 関数: mlx_key_hook
 * 説明: キーイベントフックを設定します。
 * 使用方法: int mlx_key_hook(void *win_ptr, int (*funct_ptr)(), void *param);
 * パラメータ:
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - funct_ptr: キーイベント処理関数へのポインタ。
 *  - param: 関数に渡すパラメータ。
 * 戻り値: 常に0を返します。


### mlx_expose_hook
**ファイル**: `mlx_expose_hook.c`

 * 関数: mlx_expose_hook
 * 説明: ウィンドウ再描画イベントフックを設定します。
 * 使用方法: int mlx_expose_hook(void *win_ptr, int (*funct_ptr)(), void *param);
 * パラメータ:
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - funct_ptr: 再描画イベント処理関数へのポインタ。
 *  - param: 関数に渡すパラメータ。
 * 戻り値: 常に0を返します。


### mlx_loop_hook
**ファイル**: `mlx_loop_hook.c`

 * 関数: mlx_loop_hook
 * 説明: メインループにフック関数を設定します。この関数は、イベントがないときに呼び出されます。
 * 使用方法: int mlx_loop_hook(void *mlx_ptr, int (*funct_ptr)(), void *param);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - funct_ptr: フック関数へのポインタ。
 *  - param: 関数に渡すパラメータ。
 * 戻り値: 常に0を返します。


### mlx_do_sync
**ファイル**: `mlx_do_sync.c`

 * 関数: mlx_do_sync
 * 説明: ディスプレイバッファを強制的に同期します。
 * 使用方法: void mlx_do_sync(void *mlx_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 * 戻り値: なし


### mlx_get_screen_size
**ファイル**: `mlx_get_screen_size.c`

 * 関数: mlx_get_screen_size
 * 説明: 画面のサイズを取得します。
 * 使用方法: void mlx_get_screen_size(void *mlx_ptr, int *sizex, int *sizey);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - sizex: 画面の幅を格納するためのポインタ。
 *  - sizey: 画面の高さを格納するためのポインタ。
 * 戻り値: なし


### mlx_hook
**ファイル**: `mlx_hook.c`

 * 関数: mlx_hook
 * 説明: 任意のイベントフックを設定します。
 * 使用方法: int mlx_hook(void *win_ptr, int x_event, int x_mask, int (*funct)(), void *param);
 * パラメータ:
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - x_event: フックするイベントのタイプ。
 *  - x_mask: イベントマスク。
 *  - funct: イベント処理関数へのポインタ。
 *  - param: 関数に渡すパラメータ。
 * 戻り値: 常に0を返します。


### mlx_int_wait_first_expose
**ファイル**: `mlx_int_wait_first_expose.c`

 * 関数: mlx_int_wait_first_expose
 * 説明: 最初のExposeイベントを待ちます（内部使用の関数）。
 * 使用方法: int mlx_int_wait_first_expose(void *mlx_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 * 戻り値: 常に0を返します。


### mlx_put_pixel
**ファイル**: `mlx_put_pixel.c`

 * 関数: mlx_put_pixel
 * 説明: 画像にピクセルを描画します。
 * 使用方法: void mlx_put_pixel(void *img_ptr, int x, int y, int color);
 * パラメータ:
 *  - img_ptr: mlx_new_imageで取得した画像の識別子。
 *  - x: ピクセルのX座標。
 *  - y: ピクセルのY座標。
 *  - color: ピクセルの色。
 * 戻り値: なし



### mlx_set_font
**ファイル**: `mlx_set_font.c`

 * 関数: mlx_set_font
 * 説明: フォントを設定します（未実装の可能性があります）。
 * 使用方法: int mlx_set_font(void *mlx_ptr, void *win_ptr, char *name);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - name: 設定するフォントの名前。
 * 戻り値: 常に0を返します。


### mlx_xpm_to_image
**ファイル**: `mlx_xpm_to_image.c`

 * 関数: mlx_xpm_to_image
 * 説明: XPMフォーマットの画像をMiniLibXの画像に変換します。
 * 使用方法: void *mlx_xpm_to_image(void *mlx_ptr, char **xpm_data, int *width, int *height);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - xpm_data: XPMデータへのポインタ。
 *  - width: 画像の幅を格納するためのポインタ。
 *  - height: 画像の高さを格納するためのポインタ。
 * 戻り値: 変換された画像の識別子を返します。


### mlx_xpm_file_to_image
**ファイル**: `mlx_xpm_file_to_image.c`

 * 関数: mlx_xpm_file_to_image
 * 説明: XPMファイルを読み込み、MiniLibXの画像に変換します。
 * 使用方法: void *mlx_xpm_file_to_image(void *mlx_ptr, char *filename, int *width, int *height);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - filename: 読み込むXPMファイルの名前。
 *  - width: 画像の幅を格納するためのポインタ。
 *  - height: 画像の高さを格納するためのポインタ。
 * 戻り値: 変換された画像の識別子を返します。
 * Error: NULLを返す。


### mlx_png_file_to_image
**ファイル**: `mlx_png_file_to_image.c`

 * 関数: mlx_png_file_to_image
 * 説明: PNGファイルを読み込み、MiniLibXの画像に変換します。
 * 使用方法: void *mlx_png_file_to_image(void *mlx_ptr, char *filename, int *width, int *height);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - filename: 読み込むPNGファイルの名前。
 *  - width: 画像の幅を格納するためのポインタ。
 *  - height: 画像の高さを格納するためのポインタ。
 * 戻り値: 変換された画像の識別子を返します。


### mlx_destroy_display
**ファイル**: `mlx_destroy_display.c`

 * 関数: mlx_destroy_display
 * 説明: ディスプレイを破棄します（内部使用の関数）。
 * 使用方法: void mlx_destroy_display(void *mlx_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 * 戻り値: なし


### mlx_set_window_title
**ファイル**: `mlx_set_window_title.c`

 * 関数: mlx_set_window_title
 * 説明: ウィンドウのタイトルを設定します。
 * 使用方法: void mlx_set_window_title(void *mlx_ptr, void *win_ptr, char *title);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - title: 新しいタイトル。
 * 戻り値: なし


### mlx_get_color_value
**ファイル**: `mlx_get_color_value.c`

 * 関数: mlx_get_color_value
 * 説明: 色の値を取得します。
 * 使用方法: unsigned int mlx_get_color_value(void *mlx_ptr, int color);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - color: 取得する色の値。
 * 戻り値: 色の値を返します。


### mlx_sync
**ファイル**: `mlx_sync.c`

 * 関数: mlx_sync
 * 説明: 同期操作を行います。
 * 使用方法: void mlx_sync(int action, void *param);
 * パラメータ:
 *  - action: 同期操作の種類。
 *  - param: 同期操作に使用するパラメータ。
 * 戻り値: なし


### mlx_mouse_get_pos
**ファイル**: `mlx_mouse_get_pos.c`

 * 関数: mlx_mouse_get_pos
 * 説明: マウスの現在の位置を取得します。
 * 使用方法: int mlx_mouse_get_pos(void *mlx_ptr, void *win_ptr, int *x, int *y);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - x: マウスのX座標を格納するためのポインタ。
 *  - y: マウスのY座標を格納するためのポインタ。
 * 戻り値: 常に0を返します。


### mlx_mouse_move
**ファイル**: `mlx_mouse_move.c`

 * 関数: mlx_mouse_move
 * 説明: マウスの位置を設定します。
 * 使用方法: int mlx_mouse_move(void *mlx_ptr, void *win_ptr, int x, int y);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 *  - x: マウスの新しいX座標。
 *  - y: マウスの新しいY座標。
 * 戻り値: 常に0を返します。


 ### mlx_mouse_hide
**ファイル**: `mlx_mouse_hide.c`

 * 関数: mlx_mouse_hide
 * 説明: マウスカーソルを隠します。
 * 使用方法: int mlx_mouse_hide(void *mlx_ptr, void *win_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 * 戻り値: 常に0を返します。


### mlx_mouse_show
**ファイル**: `mlx_mouse_show.c`

 * 関数: mlx_mouse_show
 * 説明: マウスカーソルを表示します。
 * 使用方法: int mlx_mouse_show(void *mlx_ptr, void *win_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 * 戻り値: 常に0を返します。


### mlx_get_visual
**ファイル**: `mlx_get_visual.c`

 * 関数: mlx_get_visual
 * 説明: ビジュアル情報を取得します。
 * 使用方法: void *mlx_get_visual(void *mlx_ptr);
 * パラメータ:
 *  - mlx_ptr: mlx_initで取得したMiniLibXの識別子。
 * 戻り値: ビジュアル情報へのポインタを返します。


### mlx_int_param_event
**ファイル**: `mlx_int_param_event.c`

 * 関数: mlx_int_param_event
 * 説明: イベントパラメータを処理します（内部使用の関数）。
 * 使用方法: int mlx_int_param_event(void);
 * 戻り値: 常に0を返します。


### mlx_int_set_win_event_mask
**ファイル**: `mlx_int_set_win_event_mask.c`

 * 関数: mlx_int_set_win_event_mask
 * 説明: ウィンドウのイベントマスクを設定します（内部使用の関数）。
 * 使用方法: int mlx_int_set_win_event_mask(void *win_ptr);
 * パラメータ:
 *  - win_ptr: mlx_new_windowで取得したウィンドウの識別子。
 * 戻り値: 常に0を返します。


### mlx_hook_exit
**ファイル**: `mlx_hook_exit.c`

 * 関数: mlx_hook_exit
 * 説明: フックを終了します（内部使用の関数）。
 * 使用方法: void mlx_hook_exit(void);
 * 戻り値: なし
