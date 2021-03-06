# tk 20141113 debugMexTest causes compilation errors on Ubuntu 32 bit
# See https://github.com/RobotLocomotion/drake/issues/553
# debugMexTester.m and debugMexTest.cpp were moved to dev
# drake_add_mex(debugMexTest debugMexTest.cpp)

if(Matlab_FOUND)
  drake_add_mex(testQuatmex testQuatmex.cpp)
  target_link_libraries(testQuatmex drakeGeometryUtil)

  drake_add_mex(testGeometryGradientsmex testGeometryGradientsmex.cpp)
  target_link_libraries(testGeometryGradientsmex drakeGeometryUtil drakeMexUtil)

  drake_add_mex(testGeometryConversionFunctionsmex testGeometryConversionFunctionsmex.cpp)
  target_link_libraries(testGeometryConversionFunctionsmex drakeGeometryUtil drakeMexUtil)
endif()

drake_add_matlab_test(NAME util/test/PassByValueMapTest COMMAND PassByValueMapTest)
drake_add_matlab_test(NAME util/test/angleDiffTest COMMAND angleDiffTest)
drake_add_matlab_test(NAME util/test/asintest REQUIRES spotless COMMAND asintest)
drake_add_matlab_test(NAME util/test/atan2test COMMAND atan2test)
drake_add_matlab_test(NAME util/test/baryTest COMMAND baryTest)
drake_add_matlab_test(NAME util/test/expmap2quatTest COMMAND expmap2quatTest)
drake_add_matlab_test(NAME util/test/foh_test COMMAND foh_test)
drake_add_matlab_test(NAME util/test/invHTTest COMMAND invHTTest)
drake_add_matlab_test(NAME util/test/matGradMultMatTest COMMAND matGradMultMatTest)
drake_add_matlab_test(NAME util/test/matHessianMultMatTest COMMAND matHessianMultMatTest)
drake_add_matlab_test(NAME util/test/mtimesTest COMMAND mtimesTest)
drake_add_matlab_test(NAME util/test/normalizeVecTest COMMAND normalizeVecTest)
drake_add_matlab_test(NAME util/test/numericalGradTest COMMAND numericalGradTest)
drake_add_matlab_test(NAME util/test/pchipDeriv_test COMMAND pchipDeriv_test)
drake_add_matlab_test(NAME util/test/taylorTest OPTIONAL lcm COMMAND taylorTest)
drake_add_matlab_test(NAME util/test/taylorVarScalarMatrixMultTest COMMAND taylorVarScalarMatrixMultTest)
drake_add_matlab_test(NAME util/test/taylorVarSqTest COMMAND taylorVarSqTest)
drake_add_matlab_test(NAME util/test/testAngleAverage COMMAND testAngleAverage)
drake_add_matlab_test(NAME util/test/testAngularvel2quatdotMatrix COMMAND testAngularvel2quatdotMatrix)
drake_add_matlab_test(NAME util/test/testAngularvel2rpydotMatrix COMMAND testAngularvel2rpydotMatrix)
drake_add_matlab_test(NAME util/test/testClosestExpmap COMMAND testClosestExpmap)
drake_add_matlab_test(NAME util/test/testCrossSum COMMAND testCrossSum)
drake_add_matlab_test(NAME util/test/testCubicSplineCoefficients COMMAND testCubicSplineCoefficients)
drake_add_matlab_test(NAME util/test/testCylindrical2cartesian COMMAND testCylindrical2cartesian)
drake_add_matlab_test(NAME util/test/testDHomogTrans COMMAND testDHomogTrans)
drake_add_matlab_test(NAME util/test/testDHomogTransInv COMMAND testDHomogTransInv)
drake_add_matlab_test(NAME util/test/testDTransformSpatialForce COMMAND testDTransformSpatialForce)
drake_add_matlab_test(NAME util/test/testDcross COMMAND testDcross)
drake_add_matlab_test(NAME util/test/testFlipExpmap COMMAND testFlipExpmap)
drake_add_matlab_test(NAME util/test/testGeometryConversionFunctionsComparison COMMAND testGeometryConversionFunctionsComparison)
# DISABLED due to #3224.
if(NOT ${CMAKE_BUILD_TYPE} STREQUAL "Debug")
  drake_add_matlab_test(NAME util/test/testGeometryGradientsComparison
                        COMMAND testGeometryGradientsComparison)
endif()
drake_add_matlab_test(NAME util/test/testMotionSubspace COMMAND testMotionSubspace)
drake_add_matlab_test(NAME util/test/testMotionSubspaceDotTimesV COMMAND testMotionSubspaceDotTimesV)
drake_add_matlab_test(NAME util/test/testOrientation COMMAND testOrientation)
drake_add_matlab_test(NAME util/test/testPopulateLCMFields REQUIRES lcm COMMAND testPopulateLCMFields)
drake_add_matlab_test(NAME util/test/testQuadFormGrad COMMAND testQuadFormGrad)
drake_add_matlab_test(NAME util/test/testQuat COMMAND testQuat)
drake_add_matlab_test(NAME util/test/testQuat2expmap COMMAND testQuat2expmap)
drake_add_matlab_test(NAME util/test/testQuat2expmapSequence COMMAND testQuat2expmapSequence)
drake_add_matlab_test(NAME util/test/testQuat2rotmat COMMAND testQuat2rotmat)
# drake_add_matlab_test(NAME util/test/testQuatConjugate COMMAND testQuatConjugate)  # FIXME: see #3313
# drake_add_matlab_test(NAME util/test/testQuatProduct COMMAND testQuatProduct)  # FIXME: see #3313
drake_add_matlab_test(NAME util/test/testQuatRotateVec COMMAND testQuatRotateVec)
drake_add_matlab_test(NAME util/test/testQuatdot2angularvel COMMAND testQuatdot2angularvel)
drake_add_matlab_test(NAME util/test/testQuatdot2angularvelMatrix COMMAND testQuatdot2angularvelMatrix)
drake_add_matlab_test(NAME util/test/testQuatdot2expmapdot COMMAND testQuatdot2expmapdot)
drake_add_matlab_test(NAME util/test/testRPY2rotmat COMMAND testRPY2rotmat)
drake_add_matlab_test(NAME util/test/testRPYdot2Angularvel COMMAND testRPYdot2Angularvel)
drake_add_matlab_test(NAME util/test/testRotmat2quat COMMAND testRotmat2quat)
drake_add_matlab_test(NAME util/test/testRotmat2rpy COMMAND testRotmat2rpy)
drake_add_matlab_test(NAME util/test/testTransform COMMAND testTransform)
drake_add_matlab_test(NAME util/test/testUnwrapExpmap COMMAND testUnwrapExpmap)
drake_add_matlab_test(NAME util/test/test_datan2 COMMAND test_datan2)
drake_add_matlab_test(NAME util/test/testqpSpline COMMAND testqpSpline)
drake_add_matlab_test(NAME util/test/trigPolySinTest REQUIRES spotless COMMAND trigPolySinTest)
drake_add_matlab_test(NAME util/test/trigPolyTest REQUIRES spotless OPTIONAL lcm COMMAND trigPolyTest)
drake_add_matlab_test(NAME util/test/tvsumtest COMMAND tvsumtest)

