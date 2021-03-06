AUTOMAKE_OPTIONS=	parallel-tests

noinst_SCRIPTS=		runtest

noinst_PROGRAMS= \
	add_from_filep \
	fopen_unchanged \
	fread \
	fseek \
	tryopen

if !WIN32_HOST
pkglib_LTLIBRARIES=	malloc.la nonrandomopen.la

malloc_la_SOURCES=	malloc.c
malloc_la_LDFLAGS=	-module -avoid-version
malloc_la_LIBADD=	${DLSYM_LIB}

nonrandomopen_la_SOURCES=	nonrandomopen.c
nonrandomopen_la_LDFLAGS=	-module -avoid-version
nonrandomopen_la_LIBADD=	${DLSYM_LIB}

# we have to do it this way, because if we choose noinst_LTLIBRARIES,
# only the .a files are built
install-pkglibLTLIBRARIES:
	@echo not installing shared objects needed only for testing
endif

EXTRA_DIST= \
	CMakeLists.txt \
	NiHTest.pm \
	runtest.in \
	${TESTS} \
	bigstored.zh \
	bigzero-zip.zip \
	bogus.zip \
	broken.zip \
	cm-default.zip \
	encrypt-aes128-noentropy.zip \
	encrypt-aes192-noentropy.zip \
	encrypt-aes256-noentropy.zip \
	encrypt-aes128.zip \
	encrypt-aes192.zip \
	encrypt-aes256.zip \
	encrypt-none.zip \
	encrypt.zip \
	encrypt_plus_extra.zip \
	encrypt_plus_extra_modified_c.zip \
	encrypt_plus_extra_modified_l.zip \
	extra_field_align_1-0.zip \
	extra_field_align_1-ff.zip \
	extra_field_align_2-0.zip \
	extra_field_align_2-ff.zip \
	extra_field_align_3-0.zip \
	extra_field_align_3-ff.zip \
	extra_field_align_4-ff.zip \
	extra_field_align_1-ef_00.zip \
	extra_field_align_1-ef_ff.zip \
	extra_field_align_2-ef_00.zip \
	extra_field_align_2-ef_ff.zip \
	extra_field_align_3-ef_00.zip \
	extra_field_align_3-ef_ff.zip \
	filename_duplicate.zip \
	filename_duplicate_empty.zip \
	filename_empty.zip \
	fileorder.zip \
	firstsecond.zip \
	firstsecond-split-deflated.zip \
	firstsecond-split-stored.zip \
	foo-stored.zip \
	incons-archive-comment-longer.zip \
	incons-archive-comment-shorter.zip \
	incons-cdoffset.zip \
	incons-central-compression-method.zip \
	incons-central-compsize-larger-toolarge.zip \
	incons-central-compsize-larger.zip \
	incons-central-compsize-smaller.zip \
	incons-central-crc.zip \
	incons-central-date.zip \
	incons-central-file-comment-longer.zip \
	incons-central-file-comment-shorter.zip \
	incons-central-magic-bad.zip \
	incons-central-magic-bad2.zip \
	incons-central-size-larger.zip \
	incons-data.zip \
	incons-ef-central-size-wrong.zip \
	incons-ef-local-id-size.zip \
	incons-ef-local-id.zip \
	incons-ef-local-size.zip \
	incons-eocd-magic-bad.zip \
	incons-file-count-high.zip \
	incons-file-count-low.zip \
	incons-file-count-overflow.zip \
	incons-local-compression-method.zip \
	incons-local-compsize-larger.zip \
	incons-local-compsize-smaller.zip \
	incons-local-crc.zip \
	incons-local-filename-long.zip \
	incons-local-filename-missing.zip \
	incons-local-filename-short.zip \
	incons-local-filename.zip \
	incons-local-magic-bad.zip \
	incons-local-size-larger.zip \
	junk-at-end.zip \
	junk-at-start.zip \
	large-uncompressable \
	manyfiles-zip.zip \
	multidisk.zip \
	rename_ok.zip \
	streamed.zip \
	streamed-zip64.zip \
	test.zip \
	test2.zip \
	test-cp437.zip \
	test-cp437-comment-utf-8.zip \
	test-cp437-fc.zip \
	test-cp437-fc-utf-8-filename.zip \
	test-utf8.zip \
	test-utf8-unmarked.zip \
	testbuffer.zip \
	testbzip2.zip \
	testdir.zip \
	testchanged.zip \
	testchangedlocal.zip \
	testcomment.zip \
	testcomment13.zip \
	testcommentremoved.zip \
	testdeflated.zip \
	testdeflated2.zip \
	testempty.zip \
	testextrabytes.zip \
	testfile.txt \
	testfile.zip \
	testfile-cp437.zip \
	testfile-plus-extra.zip \
	testfile-UTF8.zip \
	testfile2014.zip \
	teststdin.zip \
	teststored.zip \
	utf-8-standardization-input.zip \
	utf-8-standardization-output.zip \
	zip-in-archive-comment.zip \
	zip64.zip \
	zip64-3mf.zip

TESTS_ENVIRONMENT=	ZIPCMP=${top_builddir}/src/zipcmp
# ${srcdir}/runtest
#LOG_COMPILER=  ${srcdir}/runtest
TEST_EXTENSIONS= .test
TEST_LOG_COMPILER= ${builddir}/runtest
#AM_TEST_LOG_FLAGS = -s

TESTS= \
	add_dir.test \
	add_from_buffer.test \
	add_from_file.test \
	add_from_file_duplicate.test \
	add_from_file_twice_duplicate.test \
	add_from_filep.test \
	add_from_stdin.test \
	add_from_zip_closed.test \
	add_from_zip_deflated.test \
	add_from_zip_deflated2.test \
	add_from_zip_partial_deflated.test \
	add_from_zip_partial_stored.test \
	add_from_zip_stored.test \
	add_stored.test \
	add_stored_in_memory.test \
	cm-default.test \
	count_entries.test \
	decrypt-correct-password-aes128.test \
	decrypt-correct-password-aes192.test \
	decrypt-correct-password-aes256.test \
	decrypt-correct-password-pkware.test \
	decrypt-no-password-aes256.test \
	decrypt-wrong-password-aes128.test \
	decrypt-wrong-password-aes192.test \
	decrypt-wrong-password-aes256.test \
	decrypt-wrong-password-pkware.test \
	delete_add_same.test \
	delete_invalid.test \
	delete_last.test \
	delete_multiple_last.test \
	delete_multiple_partial.test \
	delete_renamed_rename.test \
	encrypt.test \
	encryption-nonrandom-aes128.test \
	encryption-nonrandom-aes192.test \
	encryption-nonrandom-aes256.test \
	encryption-remove.test \
	extra_add.test \
	extra_add_multiple.test \
	extra_count.test \
	extra_count_by_id.test \
	extra_count_ignore_zip64.test \
	extra_delete.test \
	extra_delete_by_id.test \
	extra_field_align.test \
	extra_get.test \
	extra_get_by_id.test \
	extra_set.test \
	extra_set_modify_c.test \
	extra_set_modify_l.test \
	fdopen_ok.test \
	file_comment_encmismatch.test \
	fopen_unchanged.test \
	fread.test \
	fseek_deflated.test \
	fseek_fail.test \
	fseek_ok.test \
	get_comment.test \
	junk_at_end.test \
	junk_at_start.test \
	name_locate.test \
	open_cons_extrabytes.test \
	open_empty.test \
	open_empty_2.test \
	open_extrabytes.test \
	open_file_count.test \
	open_filename_duplicate.test \
	open_filename_duplicate_consistency.test \
	open_filename_duplicate_empty.test \
	open_filename_duplicate_empty_consistency.test \
	open_filename_empty.test \
	open_incons.test \
	open_many_fail.test \
	open_many_ok.test \
	open_multidisk.test \
	open_new_but_exists.test \
	open_new_ok.test \
	open_nonarchive.test \
	open_nosuchfile.test \
	open_ok.test \
	open_too_short.test \
	open_truncate.test \
	open_zip64_3mf.test \
	open_zip64_ok.test \
	progress.test \
	rename_ascii.test \
	rename_cp437.test \
	rename_deleted.test \
	rename_fail.test \
	rename_ok.test \
	rename_utf8.test \
	rename_utf8_encmismatch.test \
	set_comment_all.test \
	set_comment_localonly.test \
	set_comment_removeglobal.test \
	set_comment_revert.test \
	set_compression_bzip2_to_deflate.test \
	set_compression_deflate_to_bzip2.test \
	set_compression_deflate_to_deflate.test \
	set_compression_deflate_to_store.test \
	set_compression_store_to_bzip2.test \
	set_compression_store_to_deflate.test \
	set_compression_store_to_store.test \
	set_compression_unknown.test \
	stat_index_cp437_guess.test \
	stat_index_cp437_raw.test \
	stat_index_cp437_strict.test \
	stat_index_fileorder.test \
	stat_index_streamed.test \
	stat_index_streamed_zip64.test \
	stat_index_utf8_guess.test \
	stat_index_utf8_raw.test \
	stat_index_utf8_strict.test \
	stat_index_utf8_unmarked_strict.test \
	stat_index_zip64.test \
	utf-8-standardization.test \
	zip-in-archive-comment.test \
	zip64_creation.test \
	zip64_stored_creation.test

#XFAIL_TESTS=


AM_CPPFLAGS=-I${top_srcdir}/lib -I../lib -I${top_srcdir}/src
LDADD=${top_builddir}/lib/libzip.la

CREATED_FILES= \
	bigzero.zip \
	manyfiles-133000.zip \
	manyfiles-65536.zip \
	manyfiles-fewer.zip \
	manyfiles-more.zip \
	manyfiles-zip64-modulo.zip \
	manyfiles-zip64.zip \
	manyfiles.zip \
	runtest

check-am: ${CREATED_FILES}

bigzero.zip: bigzero-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/bigzero-zip.zip cat 0 > ${builddir}/bigzero.zip

manyfiles.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 0 > ${builddir}/$@

manyfiles-133000.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 1 > ${builddir}/$@

manyfiles-65536.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 2 > ${builddir}/$@

manyfiles-fewer.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 5 > ${builddir}/$@

manyfiles-more.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 6 > ${builddir}/$@

manyfiles-zip64-modulo.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 3 > ${builddir}/$@

manyfiles-zip64.zip: manyfiles-zip.zip
	${top_builddir}/src/ziptool ${srcdir}/manyfiles-zip.zip cat 4 > ${builddir}/$@

runtest: runtest.in
	sed -e 's!@[s]rcdir@!${srcdir}!g' -e 's!@[a]bs_srcdir@!${abs_srcdir}!g' -e 's!@[t]op_builddir@!${top_builddir}!g' ${srcdir}/runtest.in > runtest
	chmod +x runtest

cleanup:
	rm -rf ${builddir}/sandbox-*.d[0-9]*/

CLEANFILES=${CREATED_FILES}
