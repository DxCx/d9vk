d3d9_res = wrc_generator.process('version.rc')

d3d9_shaders = files([
  '../dxgi/shaders/dxgi_presenter_frag.frag',
  '../dxgi/shaders/dxgi_presenter_vert.vert',
])

d3d9_src = [
  'd3d9_main.cpp',
  'd3d9_interface.cpp',
  'd3d9_monitor.cpp',
  'd3d9_caps.cpp',
  'd3d9_device.cpp',
  'd3d9_cursor.cpp',
  'd3d9_swapchain.cpp',
  'd3d9_format.cpp',
  'd3d9_common_texture.cpp',
  'd3d9_texture.cpp',
  'd3d9_surface.cpp',
  'd3d9_volume.cpp',
  'd3d9_common_buffer.cpp',
  'd3d9_buffer.cpp',
  'd3d9_shader.cpp',
  'd3d9_vertex_declaration.cpp',
  'd3d9_query.cpp',
  'd3d9_multithread.cpp',
  'd3d9_options.cpp',
  'd3d9_stateblock.cpp',
  'd3d9_sampler.cpp',
  'd3d9_util.cpp',
  'd3d9_initializer.cpp'
]

d3d9_dll = shared_library('d3d9'+dll_ext, d3d9_src, glsl_generator.process(d3d9_shaders), d3d9_res,
  name_prefix         : '',
  dependencies        : [ dxso_dep, dxvk_dep ],
  include_directories : dxvk_include_path,
  install             : true,
  objects             : not dxvk_msvc ? 'd3d9'+def_spec_ext : [],
  vs_module_defs      : 'd3d9'+def_spec_ext,
  override_options    : ['cpp_std='+dxvk_cpp_std])

d3d9_dep = declare_dependency(
  link_with           : [ d3d9_dll ],
  include_directories : [ dxvk_include_path ])
