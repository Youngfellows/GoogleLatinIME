
cmake_minimum_required(VERSION 3.4.1)

# 二进制码剥除
set(CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -s")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -s")

add_library(jni_latinime SHARED
			jni/com_android_inputmethod_keyboard_ProximityInfo.cpp
            jni/com_android_inputmethod_latin_BinaryDictionary.cpp
            jni/com_android_inputmethod_latin_BinaryDictionaryUtils.cpp
            jni/com_android_inputmethod_latin_DicTraverseSession.cpp
            jni/jni_common.cpp
			jni/src/dictionary/header/header_policy.cpp
			jni/src/dictionary/header/header_read_write_utils.cpp
			jni/src/dictionary/property/ngram_context.cpp
			jni/src/dictionary/structure/dictionary_structure_with_buffer_policy_factory.cpp
			jni/src/dictionary/structure/backward/v402/ver4_dict_buffers.cpp
			jni/src/dictionary/structure/backward/v402/ver4_dict_constants.cpp
			jni/src/dictionary/structure/backward/v402/ver4_patricia_trie_node_reader.cpp
			jni/src/dictionary/structure/backward/v402/ver4_patricia_trie_node_writer.cpp
			jni/src/dictionary/structure/backward/v402/ver4_patricia_trie_policy.cpp
			jni/src/dictionary/structure/backward/v402/ver4_patricia_trie_reading_utils.cpp
			jni/src/dictionary/structure/backward/v402/ver4_patricia_trie_writing_helper.cpp
			jni/src/dictionary/structure/backward/v402/ver4_pt_node_array_reader.cpp
			jni/src/dictionary/structure/backward/v402/bigram/ver4_bigram_list_policy.cpp
			jni/src/dictionary/structure/backward/v402/content/bigram_dict_content.cpp
			jni/src/dictionary/structure/backward/v402/content/probability_dict_content.cpp
			jni/src/dictionary/structure/backward/v402/content/shortcut_dict_content.cpp
			jni/src/dictionary/structure/backward/v402/content/sparse_table_dict_content.cpp
			jni/src/dictionary/structure/backward/v402/content/terminal_position_lookup_table.cpp
			jni/src/dictionary/structure/pt_common/dynamic_pt_gc_event_listeners.cpp
			jni/src/dictionary/structure/pt_common/dynamic_pt_reading_helper.cpp
			jni/src/dictionary/structure/pt_common/dynamic_pt_reading_utils.cpp
			jni/src/dictionary/structure/pt_common/dynamic_pt_updating_helper.cpp
			jni/src/dictionary/structure/pt_common/dynamic_pt_writing_utils.cpp
			jni/src/dictionary/structure/pt_common/patricia_trie_reading_utils.cpp
			jni/src/dictionary/structure/pt_common/bigram/bigram_list_read_write_utils.cpp
			jni/src/dictionary/structure/pt_common/shortcut/shortcut_list_reading_utils.cpp
			jni/src/dictionary/structure/v2/patricia_trie_policy.cpp
			jni/src/dictionary/structure/v2/ver2_patricia_trie_node_reader.cpp
			jni/src/dictionary/structure/v2/ver2_pt_node_array_reader.cpp
			jni/src/dictionary/structure/v4/ver4_dict_buffers.cpp
			jni/src/dictionary/structure/v4/ver4_dict_constants.cpp
			jni/src/dictionary/structure/v4/ver4_patricia_trie_node_reader.cpp
			jni/src/dictionary/structure/v4/ver4_patricia_trie_node_writer.cpp
			jni/src/dictionary/structure/v4/ver4_patricia_trie_policy.cpp
			jni/src/dictionary/structure/v4/ver4_patricia_trie_reading_utils.cpp
			jni/src/dictionary/structure/v4/ver4_patricia_trie_writing_helper.cpp
			jni/src/dictionary/structure/v4/ver4_pt_node_array_reader.cpp
			jni/src/dictionary/structure/v4/content/dynamic_language_model_probability_utils.cpp
			jni/src/dictionary/structure/v4/content/language_model_dict_content.cpp
			jni/src/dictionary/structure/v4/content/language_model_dict_content_global_counters.cpp
			jni/src/dictionary/structure/v4/content/shortcut_dict_content.cpp
			jni/src/dictionary/structure/v4/content/sparse_table_dict_content.cpp
			jni/src/dictionary/structure/v4/content/terminal_position_lookup_table.cpp
			jni/src/dictionary/utils/buffer_with_extendable_buffer.cpp
			jni/src/dictionary/utils/byte_array_utils.cpp
			jni/src/dictionary/utils/dict_file_writing_utils.cpp
			jni/src/dictionary/utils/file_utils.cpp
			jni/src/dictionary/utils/forgetting_curve_utils.cpp
			jni/src/dictionary/utils/format_utils.cpp
			jni/src/dictionary/utils/mmapped_buffer.cpp
			jni/src/dictionary/utils/multi_bigram_map.cpp
			jni/src/dictionary/utils/probability_utils.cpp
			jni/src/dictionary/utils/sparse_table.cpp
			jni/src/dictionary/utils/trie_map.cpp
			jni/src/suggest/core/suggest.cpp
			jni/src/suggest/core/dicnode/dic_node.cpp
			jni/src/suggest/core/dicnode/dic_node_utils.cpp
			jni/src/suggest/core/dicnode/dic_nodes_cache.cpp
			jni/src/suggest/core/dictionary/dictionary.cpp
			jni/src/suggest/core/dictionary/dictionary_utils.cpp
			jni/src/suggest/core/dictionary/digraph_utils.cpp
			jni/src/suggest/core/dictionary/error_type_utils.cpp
			jni/src/suggest/core/layout/additional_proximity_chars.cpp
			jni/src/suggest/core/layout/proximity_info.cpp
			jni/src/suggest/core/layout/proximity_info_params.cpp
			jni/src/suggest/core/layout/proximity_info_state.cpp
			jni/src/suggest/core/layout/proximity_info_state_utils.cpp
			jni/src/suggest/core/policy/weighting.cpp
			jni/src/suggest/core/result/suggestion_results.cpp
			jni/src/suggest/core/result/suggestions_output_utils.cpp
			jni/src/suggest/core/session/dic_traverse_session.cpp
			jni/src/suggest/policyimpl/gesture/gesture_suggest_policy_factory.cpp
			jni/src/suggest/policyimpl/typing/scoring_params.cpp
			jni/src/suggest/policyimpl/typing/typing_scoring.cpp
			jni/src/suggest/policyimpl/typing/typing_suggest_policy.cpp
			jni/src/suggest/policyimpl/typing/typing_traversal.cpp
			jni/src/suggest/policyimpl/typing/typing_weighting.cpp
			jni/src/utils/autocorrection_threshold_utils.cpp
			jni/src/utils/char_utils.cpp
			jni/src/utils/jni_data_utils.cpp
			jni/src/utils/log_utils.cpp
			jni/src/utils/time_keeper.cpp)

include_directories(jni/src/)

target_link_libraries(jni_latinime
                      android
                      log
					  z)