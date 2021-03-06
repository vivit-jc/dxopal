# Compatibility to DXRuby 

DXOpal has many of the DXRuby methods but some are not implemented yet. Pull Requests are welcome!

And if you are not sure how to implement, just create a issue to request them: https://github.com/yhara/dxopal/issues

## module Input

- [ ] x - TODO: pad support
- [ ] y - TODO: pad support
- [x] key_down?
- [x] key_push?
- [x] key_release?
- [ ] set_repeat
- [ ] set_key_repeat
- [ ] set_pad_repeat
- [ ] set_config
- [x] mouse_x
- [x] mouse_y
- [x] mouse_pos_x
- [x] mouse_pos_y
- [ ] set_mouse_pos
- [x] mouse_down?
- [x] mouse_push?
- [x] mouse_release?
- [ ] mouse_wheel_pos
- [ ] mouse_wheel_pos=
- [ ] mouse_enable=
- [ ] keys
- [ ] requested_close?
- [ ] set_cursor

These methods are waiting Pull Requests because I don't have a gamepad.

- [ ] pad_down?
- [ ] pad_push?
- [ ] pad_release?
- [ ] pad_num
- [ ] pad_axis
- [ ] pad_lstick
- [ ] pad_rstick
- [ ] pad_pov
- [ ] pad_lx
- [ ] pad_ly
- [ ] pad_rx
- [ ] pad_ry
- [ ] pad_pov_x
- [ ] pad_pov_y
- [ ] pads

These methods will not be supported.

- update

## module Window

- [x] loop
- [x] draw
- [x] draw_scale
- [x] draw_rot
- [ ] draw_alpha
- [ ] draw_add
- [ ] draw_sub
- [ ] draw_shader
- [ ] draw_ex
- [ ] draw_font - partially
- [ ] draw_font_ex
- [ ] draw_morph
- [ ] draw_tile
- [x] draw_pixel
- [x] draw_line
- [x] draw_box
- [x] draw_box_fill
- [x] draw_circle
- [x] draw_circle_fill
- [ ] ox
- [ ] ox=
- [ ] oy
- [ ] oy=
- [ ] get_screen_shot
- [ ] get_load
- [ ] open_filename
- [ ] save_filename
- [ ] folder_dialog
- [ ] x
- [ ] x=
- [ ] y
- [ ] y=
- [x] width
- [x] width=
- [x] height
- [x] height=
- [ ] scale
- [ ] scale=
- [ ] windowed?
- [ ] windowed=
- [ ] full_screen?
- [ ] full_screen=
- [x] real_fps
- [x] fps
- [x] fps=
- [ ] frameskip?
- [ ] frameskip=
- [x] bgcolor
- [x] bgcolor=
- [ ] resize
- [ ] active?
- [ ] running_time
- [ ] get_screen_modes
- [ ] get_current_modes
- [ ] discard
- [ ] decide
- [ ] before_call
- [ ] after_call

These methods will not be supported.

- caption
- caption=
- create
- close
- created?
- closed?
- update
- sync
- load_icon
- hWnd
- min_filter
- min_filter=
- mag_filter
- mag_filter=

## class Font

- [ ] Font.new - partially
- [x] Font.default
- [x] Font.default=
- [ ] get_width
- [x] size
- [x] fontname
- [ ] name
- [ ] italic
- [ ] weight
- [ ] auto_fitting
- [ ] info

These methods will not be supported.

- install
- dispose
- disposed?

## class Image

- [x] Image.new
- [ ] Image.load_tiles
- [ ] Image.create_from_array
- [ ] Image.load_from_file_in_memory
- [ ] Image.perlin_noise
- [ ] Image.octave_perlin_noise
- [ ] Image.custom_perlin_noise
- [ ] Image.perlin_seed
- [x] `[]`
- [x] `[]=`
- [x] compare
- [x] line
- [x] box
- [x] box_fill
- [x] circle
- [x] circle_fill
- [x] triangle
- [x] triangle_fill
- [x] fill
- [x] clear
- [ ] copy_rect
- [x] draw
- [ ] draw_font - partially
- [ ] draw_font_ex
- [ ] save
- [x] slice
- [x] slice_tiles
- [ ] dup
- [ ] clone
- [x] set_color_key
- [x] width
- [x] height
- [ ] flush
- [ ] effect_image_font
- [ ] change_hls

These methods will not be supported.

- Image.load (use Image.register and `Image.[]` instead)
- dispose
- delayed_dispose
- disposed?

## class RenderTarget
## class Shader
## class Shader::Core
## class Sound

- [ ] Sound.load_from_memory
- [x] play
- [ ] start=
- [ ] loop_start=
- [ ] loop_end=
- [ ] loop_count=
- [x] stop
- [ ] set_volume
- [ ] pan
- [ ] pan=
- [ ] frequency
- [ ] frequency=

These methods will not be supported.

- Sound.new (use Sound.register and `Sound.[]` instead)
- dispose
- disposed?

## class SoundEffect

- [x] SoundEffect.new
- [ ] add
- [x] play
- [x] stop
- [ ] save

These methods will not be supported.

- disposed?

## class Sprite

- [x] Sprite.new
- [x] Sprite.check
- [x] Sprite.update
- [x] Sprite.draw
- [x] Sprite.clean
- [x] draw
- [x] `===`
- [x] check
- [x] x
- [x] x=
- [x] y
- [x] y=
- [x] z
- [x] z=
- [x] angle
- [x] angle=
- [x] scale_x
- [x] scale_x=
- [x] scale_y
- [x] scale_y=
- [x] center_x
- [x] center_x=
- [x] center_y
- [x] center_y=
- [x] alpha
- [x] alpha=
- [x] blend
- [ ] blend= (TODO: :none, :add2, :sub)
- [ ] shader
- [ ] shader=
- [x] image
- [x] image=
- [ ] target
- [ ] target=
- [x] collision
- [x] collision=
- [x] collision_enable
- [x] collision_enable=
- [x] collision_sync
- [x] collision_sync=
- [x] visible
- [x] visible=
- [x] vanish
- [x] vanished?
- [ ] param_hash
- [ ] offset_sync
- [ ] offset_sync=
