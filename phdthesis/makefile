default: phdthesis.pdf

phdthesis.pdf: \
  makefile \
  phdthesis.tex \
  bibliography.bib \
  frontbackmatter/abstract.tex \
  frontbackmatter/acknowledgments.tex \
  frontbackmatter/bibliography.tex \
  frontbackmatter/colophon.tex \
  frontbackmatter/contents.tex \
  frontbackmatter/declaration.tex \
  frontbackmatter/dedication.tex \
  frontbackmatter/dirtytitlepage.tex \
  frontbackmatter/publication.tex \
  frontbackmatter/titleback.tex \
  frontbackmatter/titlepage.tex \
  chapters/learning_to_accomplish_goals.tex \
  chapters/problems_to_solve.tex \
  chapters/theory_and_alternatives.tex \
  chapters/a_system.tex \
  chapters/experiments.tex \
  chapters/results.tex \
  chapters/discussion.tex \
  chapters/future.tex \
  chapters/appendix_the_code.tex \
  gfx/objective_description.pdf \
  gfx/agent_environment.pdf \
  gfx/multiple_agent_environment.pdf \
  gfx/reinforcement_learning.pdf \
  gfx/perception_categorization.pdf \
  gfx/problem_complexity_versus_algorithm_adaptability.pdf \
  gfx/feedback_control.pdf \
  gfx/difference_engine_feedback_control.pdf \
  gfx/state_action.pdf \
  gfx/partially_observable.pdf \
  gfx/environment_perception_physical.pdf \
  gfx/frame_representation.pdf \
  gfx/frame_perception.pdf \
  gfx/physical_perception.pdf \
  gfx/goal_state.pdf \
  gfx/reflective_event_representation.pdf \
  gfx/communication_theory.pdf \
  gfx/learning_to_plan.pdf \
  gfx/transframe.pdf \
  gfx/serial_and_parallel_plan.pdf \
  gfx/infer_plan_effects.pdf \
  gfx/planning_machine_operations.pdf \
  gfx/planning_machine_reflective_knowledge.pdf \
  gfx/blocks_world_screenshot-1.pdf \
  gfx/mindmon-isis_world-screenshot-1.pdf \
  gfx/ladder_state_machine.pdf \
  gfx/learning_to_plan-1-goal_oriented_action_hypotheses.pdf \
  gfx/learning_to_plan-2-action_precondition_goal_occurrence_hypotheses.pdf \
  gfx/learning_to_plan-3-action_precondition_transframe_hypotheses.pdf \
  gfx/learning_to_plan-4-goal_occurrence_physical_hypotheses.pdf \
  gfx/learning_to_plan-four_step_cycle.pdf \
  gfx/concurrent_parallel_reflection_efficiency.pdf
	pdflatex phdthesis
	bibtex   phdthesis
	pdflatex phdthesis
	pdflatex phdthesis

%.pdf: %.neato makefile
	neato $< -Tpdf > $@

%.pdf: %.dot makefile
	dot -Txdot $< | dot2tex -c -ftikz -tmath > temp.tex
	pdflatex temp.tex
	rm -f temp.tex
	mv -f temp.pdf $@

%.pdf: %.png makefile
	pngtopnm $< > $<.pnm
	pnmtops $<.pnm > $<.ps
	pstopdf --resolution=print --convert $<.ps
	mv -f $<.pdf $@
#	rm -f $<.pnm
#	rm -f $<.ps

clean:
	rm -f phdthesis.pdf
	rm -f chapters/*.aux
	rm -f frontbackmatter/*.aux
	rm -f phdthesis.aux
	rm -f phdthesis.lof
	rm -f phdthesis.log
	rm -f phdthesis.lol
	rm -f phdthesis.lot
	rm -f phdthesis.out
	rm -f phdthesis.toc
	rm -f phdthesis.bbl
	rm -f phdthesis.blg

